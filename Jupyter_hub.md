# Accessing and Using JupyterHub on the AIR Lab Server<img width="1334" height="68" alt="image" src="https://github.com/user-attachments/assets/deb42b31-5e26-4f39-a8e9-5f542cb5df75" />

JupyterHub allows users to run Jupyter Notebooks directly on the AIR Lab server, providing an integrated environment for developing, executing, and sharing Python code in the cloud.

## 1. Prerequisites: Server Access via Tailscale
Before using JupyterHub, you must have remote access to the AIR Lab server through Tailscale.
If not done yet follow instruccions on [Connecting to the AirLab Remote Workstation Using Tailscale](https://github.com/airlab-tec/server_usage/blob/main/README.md)

## 2. Connecting to the AIR Lab JupyterHub
After setting up Tailscale, you can access the JupyterHub interface using the following address:
URL:  [airlabstation1.tail9513fa.ts.net](airlabstation1.tail9513fa.ts.net)
	
1. Open a web browser and navigate to the above URL.
     <img width="1457" height="706" alt="image" src="https://github.com/user-attachments/assets/9575a626-e231-4b69-afe0-7eb584715f92" />
2. Log in using your Tec de Monterrey (tec.mx) email credentials.
	
3. Once logged in, you will be directed to your personal workspace, where you can create and manage your Jupyter Notebooks.
	<img width="1465" height="720" alt="image" src="https://github.com/user-attachments/assets/43eba1fb-43c7-4b03-81ba-3ef69a4176e7" />


## 3. Recommended Environment Management: Conda
It is strongly recommended to use Conda for managing your Python environments. Conda allows you to isolate packages and dependencies, ensuring reproducible and stable notebook execution.
To create a new Conda environment within JupyterHub:
1. Open a Terminal from the JupyterHub interface.
<img width="2918" height="1436" alt="image" src="https://github.com/user-attachments/assets/343cbce8-dbc6-4448-a8b9-22625ee1cd4e" />

2. Run the following command to create a new environment named mi_env with Python 3.10:

```bash
conda create -n mi_env python=3.10 ipykernel -y
```  
3. Once the installation is complete, refresh the JupyterHub page in the browser.
<img width="1465" height="720" alt="image" src="https://github.com/user-attachments/assets/2dd45f0e-4cd5-4e61-a893-adebe9ad580f" />

4. Your new Conda environment (mi_env) will now appear in the kernel list, allowing you to select it when creating or running a notebook.
<img width="2930" height="1400" alt="image" src="https://github.com/user-attachments/assets/241f53dd-c77d-4bff-8e16-5cc7822cdc5a" />

## 4. Use of conda env

As best practices, keep in mind:
* Keep your environments lightweight by installing only the necessary packages.
* Use conda activate mi_env in the terminal to work directly within the environment.
* Regularly update Conda and its packages using conda update --all.
* Backup your notebooks periodically to avoid accidental data loss.
 
For example to create a conda env with pytorch, run:
```bash
conda create -n ml python=3.10 ipykernel 
conda activate ml
pip install torch torchvision
```

Remember that in order to be able to see a conda env in the kernel lsit you must install ipykernel in your new env example:

```bash
conda create -n <env_name>
conda activate <env_name>
conda install ipykernel
```

If the env is not avialable you can force it to apear with:
`python -m ipykernel install --user --name <env_name> --display-name "<env_name>"`

Also if you want to erase an env:
`conda remove --name <env_name> --all`


## 5. Additional: JupyterHub + Visual Studio  Code

JupyterHub can be seamlessly integrated with Visual Studio Code (VS Code) to enhance your workflow by combining the flexibility of cloud-based notebooks with the powerful features of a local development environment. This setup allows you to edit, execute, and manage Jupyter Notebooks directly from VS Code while running computations on the AIR Lab server.


### Step 1. Install VS Code and Required Extensions

Before connecting to the JupyterHub environment, ensure the following components are installed on your local computer:

1. Visual Studio Code
Download and install it from https://code.visualstudio.com.
2. Extensions Required
* Python (by Microsoft)
* Jupyter (by Microsoft)
* JupyterHub (by Microsoft)

To install extensions:
1. Open VS Code.
2. Go to View → Extensions or press Ctrl+Shift+X.
3. Search for each extension name and click Install.


### Step 2. Connect VS Code to JupyterHub

You can configure VS Code to connect directly to your JupyterHub instance:

1. Open VS Code.
2. Press Ctrl+Shift+P (or Cmd+Shift+P on macOS) to open the Command Palette.
3. Type and select “Jupyter: Specify Jupyter Server for Connections”.
4. Choose “Existing: Specify the URI of an existing server”.
5. Enter your AIR Lab JupyterHub URL, for example:
https://airlabstation1.tail9513fa.ts.net
6. When prompted, log in using your Tec de Monterrey (tec.mx) credentials. If institutional e-mail is name.last@tec.mx, your user is name.last. Then it will ask your for a password or api key, the users created by JupyterHub do not have password so you must use an api key.

Once connected, you will be able to open, edit, and execute notebooks from the JupyterHub server directly in VS Code.

### Step 3. Obtain a JupyterHub api Key


<img width="660" height="634" alt="bitmap" src="https://github.com/user-attachments/assets/f39d7b76-5690-46e2-b390-8fb2d810af47" />




