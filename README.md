# ACIT-3487-Project-1
---

# Part 2: 
## Step 1: Installing Caddy Locally Using the Terminal


### Task:
Install Caddy on your local machine using only the terminal/command line.
### Instructions:
---
#### For Windows:
1. **Open PowerShell as Administrator:**
   - Press `Windows + X` to open the quick menu, then select **Windows PowerShell (Admin)**. This will give you the necessary permissions to run installation commands.
2. **Download the Caddy Binary:**
   - In the PowerShell window, type the following command to download the latest Caddy binary:
     ```powershell
     curl "https://github.com/caddyserver/caddy/releases/latest/download/caddy_windows_amd64.zip" -o caddy_windows_amd64.zip
     ```
     - **Explanation:** This command uses `curl` to download the `caddy_windows_amd64.zip` file to your current directory. 
     - **What to expect:** The download will take a few seconds to complete.

3. **Extract the ZIP File:**
   - After the download completes, run the following command to extract the ZIP file:
     ```powershell
     Expand-Archive -Path "caddy_windows_amd64.zip" -DestinationPath "C:\Caddy"
     ```
     - **Explanation:** This extracts the contents of the ZIP file into the `C:\Caddy` folder.

4. **Navigate to the Caddy Folder:**
   - Now, change to the folder where Caddy was extracted:
     ```powershell
     cd C:\Caddy
     ```
     - **Explanation:** This command changes the current directory to `C:\Caddy`.

5. **Run Caddy:**
   - To start Caddy, use this command:
     ```powershell
     .\caddy.exe run
     ```
     - **What to expect:** After running this command, Caddy will start up and you should see logs in the PowerShell window.
     - **Next Step:** Open a web browser and go to `http://localhost:2015`. You should see Caddy’s default welcome page.

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
