User Manual Procedure
Creating and Activating a Python Virtual Environment and Installing a Package
Prerequisites
Before you begin, ensure you have the following ready:
A computer (Windows, macOS, or Linux) with Python 3.8 or higher installed.
Access to a command-line interface (Terminal on macOS/Linux or Command Prompt / PowerShell on Windows).
An existing project folder on your computer where you want to create the virtual environment.
Step-by-Step Procedure
Step 1: Open your command-line interface and navigate to your project directory.
Action: Type cd path/to/your/project-folder (replacing the path with your actual folder location) and press Enter.
Expected Result: The terminal prompt changes to show that you are now working inside your target project directory.
Step 2: Create the virtual environment.
Action: Type python -m venv venv (or python3 -m venv venv on macOS/Linux) and press Enter.
Expected Result: A new folder named venv containing the isolated Python environment files is created inside your project directory. No errors are displayed in the terminal.
Step 3: Activate the virtual environment.
Action: Run the activation command specific to your operating system:
Windows (Command Prompt): venv\Scripts\activate.bat
Windows (PowerShell): venv\Scripts\Activate.ps1
macOS / Linux: source venv/bin/activate
Expected Result: The terminal prompt updates to display (venv) at the far left, indicating that the virtual environment is successfully active.
Step 4: Verify the active Python interpreter.
Action: Type which python (macOS/Linux) or where python (Windows) and press Enter.
Expected Result: The terminal outputs a file path that points directly to the python executable inside your local venv folder rather than the global system path.
Step 5: Install a package into the virtual environment.
Action: Type pip install requests and press Enter.
Expected Result: pip downloads and installs the requests package and its dependencies, ending with a message stating Successfully installed requests-....

