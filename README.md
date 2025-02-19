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
     <img width="487" alt="Screenshot 2025-02-19 at 2 13 20 PM" src="https://github.com/user-attachments/assets/47ae0f41-0864-4d42-b671-a8b893ce3bdb" />

     - You should be now logged in inside your Virtual Machine!!

3. **Install Caddy inside the VM:**  
   - Update package list:  
     ```bash
     sudo apt update
     ```
   - Install Caddy:  
     ```bash
     sudo apt install -y caddy
     ```
     <img width="497" alt="Screenshot 2025-02-19 at 2 12 38 PM" src="https://github.com/user-attachments/assets/2989d33b-5cd2-496e-be56-5caf5b0160a2" />


4. **Start and Verify Caddy:**  
   - Run Caddy:  
     ```bash
     caddy run
     ```
   - Open a browser and visit `http://localhost:<VM's IP address>` to check if Caddy is running.

<img width="813" alt="Screenshot 2025-02-19 at 2 09 30 PM" src="https://github.com/user-attachments/assets/2cf8f48e-a290-43e6-bdb0-909e63a42a46" />

---

## Step 2: Creating a Simple Website with Login and Session
#### Task:
Create a simple website with a login form using **Python (Flask)** as the backend, **HTML** for the frontend, and **CSS** for styling.

---
### Instructions:
#### 1. Install Flask

- **Create a Python virtual environment** (optional but recommended):
  ```bash
  python3 -m venv venv
  ```
##### Activate the environment
- Linux/macOS
  ```bash
   source venv/bin/activate
  ```
- Windows:
  ```bash
   .\venv\Scripts\activate
  ```
##### Python Back-end
```bash
pip install flask
```

#### 2. Create Project files 
```
/my_project
  /templates
    login.html
  /static
    /css
      styles.css
  app.py
```
### ! All Necesssary files will be provided (HTML, CSS, PYTHON) !

#### 3.Run the Application
- macOS
  ```bash
  python3 app.py
  ```
- Windows
  ```bash
  python app.py
  ```
#### 4.Test the login 
- Enter `admin` as the username and `password` as the password to log in
- After logging in, you'll see a welcome message. Cick `logout` to log ot

  























  
