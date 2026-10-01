




from datetime import date
from typing import Optional
from fastapi import FastAPI, Header, HTTPException, status
from pydantic import BaseModel, Field

app = FastAPI(title="Goanar's Project Management API", version="1.0.0")

class TaskCreateRequest(BaseModel):
    title: str = Field(..., max_length=255)
    description: Optional[str] = None
    assignee_id: Optional[str] = None
    due_date: Optional[date] = None
    priority: Optional[str] = "medium"

@app.post("/api/v1/projects/{project_id}/tasks", status_code=status.HTTP_201_CREATED)
async def create_task(
    project_id: str,
    task_data: TaskCreateRequest,
    authorization: Optional[str] = Header(None)
):
    if not authorization or not authorization.startswith("Bearer "):
        raise HTTPException(
            status_code=status.HTTP_401_UNAUTHORIZED,
            detail="Missing or invalid authentication token."
        )
    
    return {
        "status": "success",
        "code": 201,
        "message": "Task created successfully.",
        "data": {
            "task_id": "tsk_python_lab_01",
            "project_id": project_id,
            "title": task_data.title,
            "description": task_data.description,
            "assignee_id": task_data.assignee_id,
            "due_date": str(task_data.due_date) if task_data.due_date else None,
            "priority": task_data.priority,
            "status": "todo",
            "created_at": "2026-10-01T12:15:00Z"
        }
    }

