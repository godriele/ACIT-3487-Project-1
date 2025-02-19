# ACIT-3487-Project-1
---
# Part 1: Introduction

# Part 2: Local Installation
## Step 1: Installing Caddy Locally

### Tasks
Install Caddy on your local machine using only the terminal/command line.
### Instructions:
---
#### For Windows:
1. **Visit the Official Caddy Website:**
   - Open your web browser and go to the official Caddy download page:
     - [https://caddyserver.com/download](https://caddyserver.com/download)

2. **Download Caddy for Windows:**
   - On the download page, you will see options for different operating systems.
   - Select **Windows** (amd64) as the version you need.
   - Click the **Download** button to get the latest `.zip` file (e.g., `caddy_windows_amd64.zip`).

3. **Extract the ZIP File:**
   - After the download is complete, navigate to your Downloads folder or wherever you saved the ZIP file.
   - Right-click the downloaded `.zip` file and select **Extract All...**.
   - Choose a destination for the extracted files (e.g., `C:\Caddy`).

4. **Navigate to the Caddy Folder:**
   - Open **PowerShell** as an administrator (press `Windows + X`, then select **Windows PowerShell (Admin)**).
   - Change the directory to where you extracted the Caddy files. For example:
     ```powershell
     cd C:\Caddy
     ```

5. **Run Caddy:**
   - In the PowerShell window, start Caddy with the following command:
     ```powershell
     .\caddy.exe run
     ```
     - **What to expect:** Caddy will start, and you will see logs in the PowerShell window.
     - **Next Step:** Open your browser and visit `http://localhost:2015`. You should see the default Caddy welcome page.

6. **Stop Caddy:**
   - To stop Caddy, press `Ctrl + C` in the PowerShell window.
--- 
#### For Linux (Ubuntu/Debian-based):
1. **Update System Package List:**
   - Open a terminal and run the following command to update your system:
     ```bash
     sudo apt update
     ```
     - **Explanation:** This command updates your package list, ensuring that you have the latest information on available software.

2. **Install Caddy:**
   - Run this command to download and install Caddy:
     ```bash
     curl -fsSL https://get.caddyserver.com | bash -s personal
     ```
     - **Explanation:** This command downloads the Caddy installation script from the official website and then installs Caddy.
     - **What to expect:** The installation process will take a few seconds to complete.
3. **Start Caddy:**
   - After installation, start Caddy with the following command:
     ```bash
     sudo systemctl start caddy
     ```
     - **Explanation:** This command starts the Caddy service on your machine.
4. **Verify Installation:**
   - To check if Caddy is running, type:
     ```bash
     sudo systemctl status caddy
     ```
     - **What to expect:** You should see the status of the Caddy service, indicating it's running.

5. **Access Caddy's Default Page:**
   - Open a web browser and go to `http://localhost`. You should see Caddy’s default welcome page.
---
### For macOS:
1. **Install Homebrew (if not already installed):**
   - Open a terminal and run the following command to install Homebrew (a package manager for macOS):
     ```bash
     /bin/bash -c "$(curl -fsSL https://raw.githubusercontent.com/Homebrew/install/HEAD/install.sh)"
     ```
     - **Explanation:** Homebrew is a tool that allows you to easily install software on macOS.

2. **Install Caddy Using Homebrew:**
   - Once Homebrew is installed, run this command to install Caddy:
     ```bash
     brew install caddy
     ```
     - **Explanation:** This will download and install the latest version of Caddy using Homebrew.

3. **Start Caddy:**
   - To start Caddy, use the following command:
     ```bash
     sudo caddy start
     ```
     - **Explanation:** This command starts the Caddy server.

4. **Verify Installation:**
   - Open a web browser and visit `http://localhost`. You should see Caddy’s default welcome page.
