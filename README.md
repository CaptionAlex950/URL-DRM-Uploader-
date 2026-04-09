[![Deploy To Heroku](https://www.herokucdn.com/deploy/button.svg)](https://heroku.com/deploy/?template=https://github.com/CaptionAlex950/URL-DRM-Uploader-)


# Deploying a Python Script with Requirements and Additional Tools

This guide provides step-by-step instructions to deploy a Python script by installing dependencies listed in `requirements.txt`, and additional tools `aria2c` and `ffmpeg` on macOS, Linux, and Windows. Additionally, it covers setting file permissions for binary files.

## Table of Contents

- [Prerequisites](#prerequisites)
- [Installing Dependencies](#installing-dependencies)
  - [macOS](#macos)
  - [Linux](#linux)
  - [Windows](#windows)
- [Setting File Permissions for Binaries](#setting-file-permissions-for-binaries)
  - [macOS and Linux](#macos-and-linux)
  - [Windows](#windows)
- [Running the Python Script](#running-the-python-script)

## Prerequisites

Ensure you have the following installed on your system:
- Python 3.x
- `pip` (Python package installer)

## Installing Dependencies

### macOS

1. **Install Homebrew** (if not already installed):
   ```sh
   /bin/bash -c "$(curl -fsSL https://raw.githubusercontent.com/Homebrew/install/HEAD/install.sh)"
   ```

2. **Install aria2c and ffmpeg**:
   ```sh
   brew install aria2 ffmpeg
   ```

3. **Install Python dependencies**:
   ```sh
   pip install -r requirements.txt
   ```

### Linux

#### Debian/Ubuntu

1. **Update package list and install dependencies**:
   ```sh
   sudo apt update
   sudo apt install -y aria2 ffmpeg python3-pip
   ```

2. **Install Python dependencies**:
   ```sh
   pip3 install -r requirements.txt
   ```

#### Fedora

1. **Update package list and install dependencies**:
   ```sh
   sudo dnf install -y aria2 ffmpeg python3-pip
   ```

2. **Install Python dependencies**:
   ```sh
   pip3 install -r requirements.txt
   ```

### Windows

1. **Install Chocolatey** (if not already installed):
   - Open Command Prompt as Administrator and run:
     ```sh
     @"%SystemRoot%\System32\WindowsPowerShell\v1.0\powershell.exe" -NoProfile -InputFormat None -ExecutionPolicy Bypass -Command "Set-ExecutionPolicy Bypass -Scope Process -Force; [System.Net.ServicePointManager]::SecurityProtocol = [System.Net.ServicePointManager]::SecurityProtocol -bor 3072; iex ((New-Object System.Net.WebClient).DownloadString('https://community.chocolatey.org/install.ps1'))" && SET "PATH=%PATH%;%ALLUSERSPROFILE%\chocolatey\bin"
     ```

2. **Install aria2c and ffmpeg**:
   ```sh
   choco install aria2 ffmpeg
   ```

3. **Install Python dependencies**:
   ```sh
   pip install -r requirements.txt
   ```

## Setting File Permissions for Binaries

### macOS and Linux

For macOS and Linux, you need to set the execute permissions for the binaries.

1. **Set file permissions**:
   ```sh
   chmod +x binary/macos/mp4decrypt
   chmod +x binary/linux/mp4decrypt
   ```

### Windows

For Windows, binary files typically do not require setting execute permissions, but you should ensure they are in a directory included in the system's PATH.

## Running the Python Script

Once all dependencies and tools are installed, and file permissions are set, you can run your Python script with:
```sh
python main.py
```

Replace `main.py` with the name of your Python script file.

---

By following the instructions above, you should be able to set up and run your Python script with all required dependencies and tools on macOS, Linux, and Windows. If you encounter any issues, ensure all steps are followed correctly and refer to the respective package manager's documentation for further assistance.
