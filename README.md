# ACIT-3487-Project-1
---
# Part 1: Introduction
# Part 2: Local Installation
## Step 1: Installing Caddy Using Multipass
### Tasks
Install Caddy inside a Multipass virtual machine to keep it isolated from your main system.
### Instructions:
---
### For Windows, Linux, and macOS (Using Multipass)
1. **Install Multipass:**  
   - **Windows (PowerShell):**  
     ```powershell
     winget install Canonical.Multipass
     ```
   - **Linux/macOS (Terminal):**  
     ```bash
     sudo snap install multipass
     ```
   - Verify installation:  
     ```bash
     multipass version
     ```
2. **Launch an Ubuntu Virtual Machine:**  
   - Create a VM named `caddy-vm`:  
     ```bash
     multipass launch --name caddy-vm
     ```
   - Check if the VM is running:  
     ```bash
     multipass list
     ```
   - Access the VM:  
     ```bash
     multipass shell caddy-vm
     ```
3. **Install Caddy inside the VM:**  
   - Update package list:  
     ```bash
     sudo apt update
     ```
   - Install Caddy:  
     ```bash
     sudo apt install -y caddy
     ```
4. **Start and Verify Caddy:**  
   - Run Caddy:  
     ```bash
     caddy run
     ```
   - Open a browser and visit `http://localhost:2015` to check if Caddy is running.

