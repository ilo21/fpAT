# <div align="center">fpExplorer<br><br>![icon64x64](https://user-images.githubusercontent.com/87764674/174671214-01d6a9e9-39bc-4bd4-8a02-e519a0bd834f.png)<br> [![License: GPL v3](https://img.shields.io/badge/License-GPLv3-blue.svg)](https://www.gnu.org/licenses/gpl-3.0) [![Created my free logo at LogoMakr.com](https://img.shields.io/badge/Created%20my%20free%20logo%20at-LogoMakr.com-blue)](https://logomakr.com/)
  <br></div>
## What is it?
fpExplorer is an open-source application that allows users to preview and perform basic analysis of fiber photometry data recorded using Tucker Davis Technologies (TDT) systems. To make the application useful to the researchers who do not use TDT system, we added support for generic csv files. <br>This is our attempt to standardize and simplify analysis approaches.<br>
<br>![example_github](https://github.com/ilo21/fpExplorer/assets/87764674/db595b39-110a-413f-9d57-6032ef10e104)<br>
<br>
![batch-z-score-options](https://github.com/ilo21/fpExplorer/assets/87764674/6570e972-dc5a-4d3e-8117-e6c91f756199)
<br>
## Usage
We provide users with a Python source code as well as an independent windows application that does not require any programming background. (See the detailed [Application Guide](https://github.com/ilo21/fpExplorer/blob/main/fpExplorer_src/Documentation/docs.pdf) and [Installation](#installation) instructions.)<br>
<br><br>
![Flow](https://user-images.githubusercontent.com/87764674/174672419-8a7a6296-88f5-40da-a291-fd0218cd0c15.png)
<br>
## Optional Peri Event Video Extraction
In order to be able to preview the recorded signal around our events together with the recorded videos, we developed a small additional application: [fpVideoExplorer](https://github.com/ilo21/fpExplorer/tree/main/fpVideoExplorer_src). 
## Installation
- Windows application: <br>
The installation file for the desktop application is available [here](https://github.com/ilo21/fpExplorer/releases). Download the fpExplorer.Installer.exe file and run it.
## Development
- Install [Anaconda](https://www.anaconda.com/products/individual) Python Distribution.
- Create a separate environment for the development.
  - From [yml](https://github.com/ilo21/fpExplorer/blob/main/environment_info/fpExplorer_env.yml) file:
    - Download or clone the repository. Open Anaconda navigator and start CMD.exe Prompt (on MacOS: open Terminal). Change directory to the folder where yml file is located and type (replace "Path_to_cloned_repo" with your own path):
    ```
    cd C:\Path_to_cloned_repo\fpExplorer\environment_info
    ```
    - Next, type:
    ```
    conda env create -f fpExplorer_env.yml
    ```
  - From scratch:
      - Open Anaconda navigator and start CMD.exe Prompt (Windows) or open Terminal (on MacOS) and type:
      ```
      conda create --name fpExplorer python=3.7
      ```
      - Change change your working environment to the new environment:
      ```
      conda activate fpExplorer
      ```
      - Install required packeges one by one:
      ```
      pip install tdt
      pip install pandas
      pip install scipy
      pip install sklearn
      pip install matplotlib
      pip install PyQt5
      pip install pyqtgraph
      ```
- Change your working environment to the new environment (if you haven't already):
```
conda activate fpExplorer
```
- Navigate to fpExplorer_src folder and run:
```
python fpExplorer.py
```
You can find more information about managing conda environments [here](https://conda.io/projects/conda/en/latest/user-guide/tasks/manage-environments.html).
## Troubleshooting installation of python packages
Here are some of the packeges with which we had problems installing on MacOS and the solutions that worked for us:
```
pip3 install --no-build-isolation scikit-learn
conda install -c conda-forge pyqt
```
## Limitations
This application was developed to meet the needs of researchers at Linköping University (LiU), Sweden. We have tried to make fpExplorer easily accessable (no programming knowledge required) and broadly applicable (as long as datafiles were created with TDT's [Synapse software](https://www.tdt.com/component/synapse-software/) or were exported to standard csv files and formatted according to our [guidelines](https://github.com/ilo21/fpExplorer/blob/main/fpExplorer_src/Documentation/docs.pdf)). However, we do realize that each research group might have their own, custom fiber photometry setups and unique experimental designs, and our analysis tool will not be able to handle all of the cases.
- The application was developed and extensively tested on Windows 10 and Windows 11 platform. We have only minimally tested running it on MacOS (Big Sur 11.7) and Linux systems.
- Our application requires a very proprietary folder structure that is characteristic to [TDT](https://www.tdt.com/docs/synapse/managing-data-for-your-lab/) software (Subject-> Experiment or Experiment->Structure)
- Currently supported events are only the ones that don't start with Cam or Tick (e.g., "PrtA 253", "Note 1")
## Contributors
- [Ilona Szczot](https://liu.se/en/employee/ilosz01) (development and analytical expertise)
- [Joost Wiskerke](https://liu.se/en/employee/joowi80) (development and analytical expertise)
- [Johan Skold](https://liu.se/medarbetare/johsk39) (extensive testing and invaluable feedback)
- [David Barker](https://www.thebarkerlab.com/) (we were inspired by his group's [pMAT](https://github.com/djamesbarker/pMAT) (Photometry Modular Analysis Tool))
- [Patrick Mulholland](https://education.musc.edu/MUSCApps/facultydirectory/Mulholland-Patrick) (provided a modified polynomial fitting method)






