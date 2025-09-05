# Drone Obstacle Detection 
TerraWing is a service for obstacle detection and classification on UAV flight paths.  
Our solution is designed for use in the agricultural sector.  

## Uniqueness
- High system performance  
- Project already at MVP stage  
- Use of modern AI-based detection methods  

## Future Development
- [ ] Specialized dataset  
- [ ] AI plugins deployable on the server to handle different tasks  
- [ ] Automatic mapping of the drone’s work area  
- [ ] Collaborative operation of multiple UAVs  
- [ ] Integration with weather services  

# Getting Started  

### Install pyenv for Python version management  
- Windows (Chocolatey): `choco install pyenv-win`  
- Linux/macOS: `curl https://pyenv.run | bash`  

Check available Python versions with: `pyenv install --list`  
Install Python 3.11 or higher: `pyenv install 3.11.8`  

### Install poetry (package manager)  
- Windows PowerShell:  
  `(Invoke-WebRequest -Uri https://install.python-poetry.org -UseBasicParsing).Content | py -`  
- Linux/macOS:  
  `curl -sSL https://install.python-poetry.org | python3 -`  

### Virtual Environment  
If you are using `pyenv`, run the following commands:  
- `poetry config virtualenvs.prefer-active-python true`  
- `pyenv local <python version number, e.g., 3.11.8>`  

Prepare the virtual environment for poetry:  
`poetry use env <python version number, e.g., 3.11.8>`  

Activate the environment: `poetry shell`  
Install dependencies: `poetry install`  

Copy the settings template:  
- Windows: `copy .env.dist .env`  
- Linux/macOS: `cp .env.dist .env`  

Edit `.env` with your configuration...  

### Run the Server  
Run: `python app.py`  

# Development  

## Contribution Guidelines  
- **Linter**: `ruff`  
  Run with: `poetry run ruff check src`  
- **Code formatter**: `black`  
  Run with: `poetry run black src`  

## Server Tests  
Inside the `tests` folder, you will find `test_video_stream.py`.  
This script simulates a drone by streaming either a video file or your webcam to the server.  

To stream a pre-recorded video:  
```bash
python test_video_stream.py <drone_id> <drone_secret> --video_source <path>

