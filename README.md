# SuperCam Dashboard

## Project Scope :
SuperCam Dashboard is composed by two Jupyter Notebooks with the following goals in mind:
 - Synthesize SuperCam downlink data to assist ePDLs in decision making.
 - Generate a status flag and condition code report for debugging at I-CMD level.

## Configuration and version identification : 
 - Supplier : CNES (DNO/SC/3S)
 - Contact name: Alex Blasco Braso
 - Contact email: alex.blasco-braso@cnes.fr
 - Confidentiality : diffusion limited to project members
 - Version date: 11/12/2020 - November 12, 2020
 - Version number: 1.0  
 - Reference version number: -
 - Version objective: Standalone version for ORT-11.  

## Installation
1. Download the latest release of SuperCam Dashboard [Click here to download](https://github.jpl.nasa.gov/CS3/credss/releases) wherever your heart desires.
2. Access to the GDS Starting Line with your crendetials and open Jupyter Hub:
   - For external JPL users: [Jupyter Hub External](https://jupyterhub.sops.m20.jpl.nasa.gov)
   - For internal JPL users: [Jupyter Hub Internal](https://jupyterhub-int.sops.m20.jpl.nasa.gov)
3. Start the JupyterLab server. (This may take a few minutes, but is only required if you haven’t logged in for more than a few days)
4. Once you are your JupyterLab workspace, open JupyterLab File Browser: (Ctrl + Shift + F)
5. Drag and drop the `supercam-dashboard-1.0.zip` file that you just downloaded to your JupyterLab File Browser.
6. In the Launcher's tab, click on Terminal to start a new terminal session (if you want to open a new Launcher tab the shortcut is (Ctrl + Shift + L))
8. In the JupyterLab's Terminal, Run ```unzip supercam-dashboard-1.0.zip``` to unzip the `supercam-dashboard-1.0.zip` file. 
9. Run ```rm -r supercam-dashboard-1.0.zip``` to remove the `supercam-dashboard-1.0.zip` file if you want to have a clean workspace.
7. Run `csso_login`. Select a venue by number and enter your credentials; you may be prompted for TFA via Duo. Accept it to generate an AWS token.
10. Run ```pip install panel``` to install the Panel library. This is just a temporary solution, this library will be integrated into the next GDS version.
11. Congratulations! You have successfully installed SuperCam Dashboard.

**Remember: csso_login must be executed every 8 hours.**

**Remember: By now, panel library must be installed every time you start the JupyterLab server.**

## Usage of supercam-dashboard
 - `notebooks` : Is the only folder that you really need to access to open the notebooks to execute during operations. Contains:
   - 1.0_supercam-dashboard_ab.ipynb: Synthesize SuperCam downlink data to assist ePDLs in decision making.
   - 1.0_supercam-condition-code-status-flag_ab: Generate status flag and condition code dataframe for debugging at I-CMD level.
 - `reports` : Will contain the exported reports in PDF or HTML of your notebooks. This functionality is not implemented yet.
 - `mappings` : Contains the mappings needed to identify Channels, Condition Codes and Op Codes. If you respect the naming convention, you can modify mapped values to customize your Notebook.
 - `src` : Contains the source code.

1. Open the notebooks folder
2. Double click on the notebook that you want to execute.
3. Set the beginTime and the endTime that you need in the cell displayed at the top of the notebook.
4. Click on ```Restart the kernel, then re-run the whole notebook``` (the double arrow play button) to sequencially execute the notebook cells.

**Please be patient, some cells may take a few seconds to finish its execution.**

## Authentication additional information
SuperCam Dashboard utilizes M2020 Single Sign-On (SSO) for authentication, which itself uses tokens to confirm your identify. To generate a token, run `csso_login`
Enter your LDAP crendetials as requested; depending on the venue whose data you wish to access you may be prompted for TFA via Duo.
SuperCam Dashboard will use the generated token without any further interaction required, for 8 hours as per CSSO. 

**If any of the SuperCam Dashboard utilities tell you that your SSO token has expired, re-run the token generator.**

## Notebook naming convention
version_2-4 word description_developer-initials.ipynb -> 1.0_supercam-dashboard_ab.ipynb
