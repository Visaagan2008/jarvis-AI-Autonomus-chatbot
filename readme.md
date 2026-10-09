# Jarvis Desktop Assistant

Jarvis is a standalone, locally-hosted AI desktop assistant for Windows. It combines a sleek system console dashboard with powerful local AI inference and deep system integration, allowing you to monitor and control your machine autonomously.

## Features

* **Local AI Processing:** Powered by [Ollama](https://ollama.com/), Jarvis runs offline inference using the `llama3.2` model, ensuring your data never leaves your machine.

* **Desktop UI & Embedded Frontend:** Built with `pywebview` and a local HTTP server. The UI is a fully embedded, base64-encoded HTML/CSS/JS system console dashboard—no external web assets required.

* **System Integration & Control:** Executes PowerShell commands natively (`run_ps1`) to:
  * Fetch hardware and system specifications.
  * Monitor background processes.
  * Run autonomous host commands.

* **Standalone Executable:** Available as a compiled Windows executable for seamless deployment without requiring a Python environment.

## Prerequisites

If you are running the compiled executable, you only need:

* **Windows OS** (due to PowerShell integrations)
* **Ollama:** Installed and running locally.
* **Llama 3.2:** You must pull the model via Ollama before running Jarvis:
  ```bash
  ollama run llama3.2
  ```

If you are running from source, you will also need:

* Python 3.8+
* `pywebview` and any other dependencies listed in the environment setup.

## Installation and Usage

### Option 1: Running the Executable (Recommended)

1. Ensure Ollama is running in the background with the `llama3.2` model available.
2. Download and run the compiled Windows executable.
3. The Jarvis system console dashboard will launch automatically in a new window.

### Option 2: Running from Source

1. Clone the repository.
2. Install the required Python dependencies:
   ```bash
   pip install pywebview requests
   ```
3. Run the main application file:
   ```bash
   python jarvis_source.py
   ```

## Project Structure

* `jarvis_source.py`: The core application code. Contains the local HTTP server logic, the `pywebview` wrapper, PowerShell execution hooks, Ollama API routing, and the base64-encoded frontend assets.
* Executable: The compiled binary of `jarvis_source.py` for easy distribution.

## Disclaimer

This application executes PowerShell commands on your host machine to monitor and manage system resources. Please review the source code (`jarvis_source.py`) if you plan to modify the autonomous host command features to ensure system stability and security. 

**Liability:** By using this software, you acknowledge that the author is not responsible for any harm, data loss, system instability, or other damages caused to your system. Use this application entirely at your own risk.