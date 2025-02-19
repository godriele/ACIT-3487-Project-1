# ACIT-3487-Project-1
---

# Part 2: 
## Step 1: Installing Caddy Locally Using the Terminal

### Task:
Install Caddy on your local machine using only the terminal/command line.

### Instructions:
### For Windows:
1. **Open PowerShell:**
   - Press `Windows + X` and select **Windows PowerShell (Admin)**.
2. **Download and Install Caddy:**
   - Run the following command to download the latest Caddy binary:
     ```powershell
     Invoke-WebRequest -Uri "https://github.com/caddyserver/caddy/releases/latest/download/caddy_windows_amd64.zip" -OutFile "caddy.zip"
     ```
3. **Extract the Caddy Binary:**
   - Extract the downloaded `.zip` file:
     ```powershell
     Expand-Archive -Path "caddy.zip" -DestinationPath "C:\Caddy"
     ```
4. **Navigate to the Folder:**
   - Change the directory to where the Caddy executable is located:
     ```powershell
     cd C:\Caddy
     ```
5. **Run Caddy:**
   - To start Caddy, use the following command:
     ```powershell
     .\caddy.exe run
     ```
   - Open a browser and visit `http://localhost:2015` to confirm the installation.

---
### For Linux (Ubuntu/Debian-based):
1. **Update System Package List:**
   - Open a terminal and run:
     ```bash
     sudo apt update
     ```
2. **Download and Install Caddy:**
   - Run the following command to download and install Caddy:
      ```bash
     curl -fsSL https://get.caddyserver.com | bash -s personal
      ```
3. **Start Caddy:**
   - Start Caddy with:
     ```bash
     sudo systemctl start caddy
     ```
4. **Verify Caddy Installation:**
   - To ensure it's running, check the status:
     ```bash
     sudo systemctl status caddy
     ```
5. **Access Caddy's Default Page:**
   - Open a web browser and go to `http://localhost`. You should see Caddy’s default welcome page.
---
### For macOS:
1. **Install Homebrew (if not already installed):**
   - Open a terminal and run:
     ```bash
     /bin/bash -c "$(curl -fsSL https://raw.githubusercontent.com/Homebrew/install/HEAD/install.sh)"
     ```
2. **Install Caddy Using Homebrew:**
   - If Homebrew is already installed, run:
     ```bash
     brew install caddy
     ```
3. **Start Caddy:**
   - To start Caddy, use the following command:
     ```bash
     sudo caddy start
     ```
4. **Verify Caddy Installation:**
   - Open a browser and navigate to `http://localhost`. You should see Caddy’s default page.

