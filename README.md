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
    home.html
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

---
## Step 3: Configure Caddy to serve the Website Locally
### Task: 
Configure the CaddyFile to serve the simple website locally. This includes setting up reverse proxy or static file serving as required for your project 

### Instructions:

#### 1. **Run Flask App**:
Make sure your Flask app is running on a specific port (e.g., `5000`). The default for Flask is port `5000`, so run the following command:

```bash
flask run --host=0.0.0.0 --port=5001
```
- This will start your Flask application, making it accessible at http://<VM-IP>:5001.

#### 2. Create and Configure Caddyfile
The Caddyfile is where you configure how Caddy will serve your website.
- Create a Caddyfile: Navigate to /etc/caddy/ (or wherever Caddy is installed on your VM) and create a Caddyfile. You can do this with any text editor. For example, use nano:
```bash
   sudo nano /etc/caddy/Caddyfile
```

- Add the following configuration to reverse proxy requests: In the Caddyfile, configure Caddy to reverse proxy incoming requests to your Flask application.

- <img width="459" alt="Screenshot 2025-02-19 at 3 30 20 PM" src="https://github.com/user-attachments/assets/1ea73f75-1dea-46f5-9c6c-5324fbb8ff3e" />

```bash
   :80 {
       reverse_proxy <ip address of your flask application>:5001
   }
```

- <img width="422" alt="Screenshot 2025-02-19 at 3 31 03 PM" src="https://github.com/user-attachments/assets/42e3665e-8eab-4851-9ebf-cd787d4e76c6" />



- This configuration tells Caddy to listen on port 80 (the default HTTP port) and forward requests to your Flask app running on port 5001.

#### 3. Restart Caddy
After you’ve updated your Caddyfile, you need to restart the Caddy service for the changes to take effect. Use the following command:
```bash
sudo systemctl restart caddy
```
#### 4. Verify the Flask App is Server by Caddy:
Open a browser and visit http://<VM-IP>. If everything is configured correctly, you should see your Flask app being served by Caddy.

 <img width="554" alt="Screenshot 2025-02-19 at 3 31 43 PM" src="https://github.com/user-attachments/assets/7ea02584-06ea-4d39-b61e-3342406f8f75" />

- We are now able to see our flask application using our VM's IP address

# Part 3: Cloud deployment on AWS EC2 instance 

Create An Ec2 Instance which allows http/https connections


![Screenshot 2025-02-20 144227](https://github.com/user-attachments/assets/ce220bb3-3f0c-4eae-9ea1-35149d0d26e5)

'''
sudo apt install -y debian-keyring debian-archive-keyring apt-transport-https
curl -1sLf 'https://dl.cloudsmith.io/public/caddy/stable/gpg.key' | sudo tee /etc/apt/trusted.gpg.d/caddy-stable.asc
curl -1sLf 'https://dl.cloudsmith.io/public/caddy/stable/debian.deb.txt' | sudo tee /etc/apt/sources.list.d/caddy-stable.list
sudo apt update && sudo apt install caddy -y
sudo systemctl start caddy
sudo systemctl enable caddy

'''

Run these commands to download and get caddy running
  
![Screenshot 2025-02-19 132918](https://github.com/user-attachments/assets/56a10e48-5284-4fcc-8e66-421944aad38a)

Purchased the domain through namecheap and setup the dns records

![Screenshot 2025-02-20 144515](https://github.com/user-attachments/assets/7af0e0c1-3c7d-4fcf-bec7-6432bca14314)

Adjust our caddy file to include our domain and reverse proxy our ip address under port 5000

![Screenshot 2025-02-20 144617](https://github.com/user-attachments/assets/6ca5c5ab-5875-4821-bb8c-2bbb676b64c1)

# Part 4:

After uploading our website files and setting permissions correctly using the following code we can viewour fuctional login.

'''
sudo chown -R www-data:www-data /var/www/html
sudo chmod -R 755 /var/www/html
'''
![Screenshot 2025-02-20 144830](https://github.com/user-attachments/assets/369cf018-666a-49ed-a7bb-bf304b57d517)



