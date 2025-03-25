[[Python]]

#### What is uv?

uv is a high-performance Python package manager built in Rust. It aims to simplify dependency management, virtual environment creation, and package installation with speed and ease. It can replace pip, pip-tools, and virtualenv in many workflows.

## Step 1: Installation

To use uv, you need to install it. It’s available via various methods depending on your operating system.

#### On macOS/Linux:

`curl -LsSf https://astral.sh/uv/install.sh | sh`

#### Via pip (alternative):

`pip install uv`

## Step 2: Creating a Virtual Environment

uv makes virtual environment management simple and fast.

1. Create a virtual environment in the current directory:
	```bash
uv venv
```

1. activate the virtual environment:
	```bash
source .venv/bin/activate
```
1. Deactivate when done:
```bash
	deactivate
```
## Step 3: Installing Packages
1. Install a single package:
```bash
uv pip install requests
```
2. Install multiple packages:
```bash
uv pip install requests numpy pandas
```
3. Install from a requirements.txt file:
```bash
uv pip install -r requirements.txt
```
## Step 4: Managing Projects with uv

1. Initialize a new project:
```bash
uv init my_project
```
This creates a my_project directory with a basic pyproject.toml.
2. Navigate into the project:
```bash
cd my_project
```
3.  Add dependencies:
```bash
uv add flask
```
This updates pyproject.toml with flask as a dependency and installs it.
4. Remove dependencies:
```bash
uv remove flask
```
5. Sync the environment with the project’s dependencies:
```bash
uv sync
```
## Step 5: Running Python Scripts

1. Run a script directly
```bash
uv run python my_script.py
```
2. Run a module:
```bash
uv run -m http.server
```
## Step 6: Exporting Dependencies

To share your project, export dependencies to a requirements.txt file:

```bash
uv pip freeze > requirements.txt
```

# Key Features and Tips

- **Speed**: uv is significantly faster than pip due to its Rust implementation.
- **Resolver**: It includes a dependency resolver to avoid conflicts.
- **Lock Files**: Use uv lock to generate a uv.lock file for reproducible builds (experimental feature as of early 2025).
- **Global Installs**: Use uv pip install --system for system-wide installs (not recommended unless necessary).

### Example Workflow

Here’s a quick example of setting up a Flask project:

```bash
# Create project
uv init flask_app
cd flask_app

# Add Flask
uv add flask

# Create a simple app
echo 'from flask import Flask
app = Flask(__name__)

@app.route("/")
def hello():
    return "Hello, World!"
' > app.py

# Run the app
uv run python app.py
```

### Troubleshooting

- **Command not found**: Ensure uv is in your PATH after installation.
- **Permission issues**: Add --user to pip install uv if needed.
- **Updates**: Keep uv updated with uv self update.

---

That’s it! You’re now equipped to use uv for Python package and project management. For more details, check the official documentation at [astral.sh/uv](https://astral.sh/uv) or run uv --help.

Let me know if you’d like deeper explanations or examples!