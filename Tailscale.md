# Connecting to the AirLab Remote Workstation Using Tailscale
## 1. Introduction
This guide explains how to connect securely to the AirLab remote workstation using Tailscale. Tailscale creates a private, encrypted network between your devices, allowing you to access the lab workstation as if it were on your local network.

## 2. Requirements

In order to connect to the server, make sure you have:
* A registered Tailscale account (with an email different from your institutional email).
* The Tailscale client installed on your computer.
* Access to a shared device.


## 3. Step-by-Step Guide

### Step 1. Install Tailscale

On Windows:
Go to https://tailscale.com/download.
Download and install the Windows client.
Launch Tailscale from the Start Menu.

On macOS:
Go to the same link.
Download the macOS version and install the .pkg file.
Open Tailscale from Applications.

On Linux:
Run the following commands:
```bash
curl -fsSL https://tailscale.com/install.sh | sh
sudo tailscale up
```

### Step 2. Sign In to Tailscale

Open the Tailscale application.
Sign in using your email address (different from your institutional email).

During first login, **skip the introduction**:

<img width="890" height="516" alt="bitmap" src="https://github.com/user-attachments/assets/68ad4e2a-cffc-46c5-bed8-45711bf86fa4" />


Once connected, your device will appear in your Tailscale network in your admin console: https://login.tailscale.com/admin/machines

<img width="2908" height="1038" alt="image" src="https://github.com/user-attachments/assets/da44d9bf-bb95-4712-adab-048156db07cd" />

### Step 3. Request Access to the AirLab Workstation
Contact the AirLab administrator and request that the lab workstation be shared with you using Tailscale’s Share Device feature. For this send an e-mail to enrico.mendez@tec.mx requesting access and sharing the e-mail linked to your tailscale account.

The administrator will share access directly to your Tailscale account by sending you an email which will receive, click accept:

<img width="376" height="337" alt="image" src="https://github.com/user-attachments/assets/4119e004-ae88-46da-b9dd-45bff09b538d" />

Then accept in the tailscale page:

<img width="338" height="342" alt="image" src="https://github.com/user-attachments/assets/fb1ee1ba-7ea7-4a3f-af35-b53e8924714c" />

Once approved, the workstation will appear under Shared Devices in your Tailscale interface in the admin console (https://login.tailscale.com/admin/machines)
<img width="2914" height="1134" alt="image" src="https://github.com/user-attachments/assets/bc59e088-47ec-4251-92eb-285a3bf3090a" />


### Step 4. Copy the Workstation IP
In the Tailscale app or web interface, locate the shared AirLab workstation.
Copy the Tailscale IP address (it usually looks like 100.x.x.x).
<img width="2914" height="1134" alt="image" src="https://github.com/user-attachments/assets/c7be3fb3-4c9d-4bcd-80e6-632c5524566a" />

### Step 7. Test connection via ping

Test the connection to the server by sending a ping to de assigned IP. You can copy the link from the admin console at tail scale
Run:
Ping 100.x.x.x

### Step 6. Connect via SSH (need user and password skip if not available)

Use the copied IP to access the workstation securely.
On your terminal run:
```bash
ssh your_username@100.x.x.x
```

When prompted, confirm the connection and enter your AirLab credentials.

### Step 7. Disconnecting

To finish your session:
Type exit in the terminal to close the SSH connection.

