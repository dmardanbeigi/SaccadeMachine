# SaccadeMachine
SaccadeMachine is an open source software for analyzing Pro-Saccade and Anti-Saccade tasks. The software is written in Python with a simple and user friendly user interface that can be run as a notebook in Jupyter. No programming knowledge is required for using the software!

See the paper for more information about the software:

Diako Mardanbegi, Thomas Wilcockson, Pete Sawyer, Hans Gellersen, and Trevor Crawford. 2019. SaccadeMachine: software for analyzing saccade tests (anti-saccade and pro-saccade). In Proceedings of the 11th ACM Symposium on Eye Tracking Research & Applications (ETRA '19). ACM, New York, NY, USA, Article 72, 8 pages. DOI: https://doi.org/10.1145/3317956.3318148 

# Assumptions
--  All the eye tracking data for the experiment should be inside a subfoler (with any arbitrary name) in the "dataset" folder.
--  Each recording should be a .csv file with the following necessary columns:
* **'GAZE_X','GAZE_Y'**: gaze coordinates in the screen 
* **'IN_SACCADE'**: saccade events. 1 during saccade otherwise 0 
* either **'IN_FIXATION'** or **'FIXATION_INDEX'**: indicating the fixation events
* **'SAMPLE_MESSAGE'**: experiment messages indicating the following events: 
        'FIXATION_TARGET_ONSET': when the fixation target appears
        'FIXATION_TARGET_OFFSET': when the fixation target disappears
        'TARGET_ONSET': when the main target appears. Use the same msg when distractor appears in anti-saccade test. 
        'TARGET_OFFSET': when the main target disappears. Use the same msg when distractor disappears in anti-saccade test. 
* **'TIMESTAMP'**: timestamp in ms
* **'TRIAL_INDEX'**: trial index 
* **'TARGET_X','TARGET_Y'**: target location in the screen for pro-saccade experiments.
* **'DISTRACTOR_X','DISTRACTOR_Y'**: location of the distractor in the screen used in anti-saccade or recent-distractor experiments.
* **'IN_BLINK'** column is optional.

-- If the participants are divided into groups, provide an extra column (named as **'SUBJECT_GROUP'**) indicating group index.

-- File name should match the subject name and has to be capital. Name column in the recording is optional but if it exists it has to match the file name. All the names will be converted to capital letters in the result files. 

-- The center fixation target is assumed to be located at the center of the screen. 

-- The recording could consist of multiple blocks (e.g., a few pilot trials at the beginning). The **'BLOCK'** columns should be provided in the recording indicating the block index. It does not matter if the trial indices are reset to 1 in each block. 

-- The recording could also have multiple conditions. Provide an extra column **'CONDITION'** in the recording to show the condition label (string or integer) of each trial.  


# Installation

**1**- Download and install python 3.6.x from https://www.python.org/downloads/

-- **Mac**:

**2**- Open the terminal (find the Terminla in \Applications\Utilities\terminal)

**3**- Go to the installation folder from your terminal (you can just write cd, press spacebar once and drag the installation folder into the terminal): 
```cd <path to your installation folder>```

**4**- run the following lines:
```pip3 install -r requirements_mac.txt```
and then 
```jupyter contrib nbextension install --user```

-- **Windows**:

**2**- Search for cmd.exe, right click and run that as admin

**3**- From your cmd, go to the installation folder:
```cd <path to your installation folder>```

**4**- Run the following lines (you may need to download and install git from https://git-scm.com/downloads
if you got a git related error after the first line): 
```pip3 install -r requirements_win.txt```
and then 
```jupyter contrib nbextension install --system```


Installation may take a few minutes and it shouldn't return any error. After the installation close the terminal.
 
# First time running the software

**1**- You need to make sure that there is a folder named "dataset" inside your SaccadeMachine folder and it contains the AS, PS and RD datasets

**2**- Go to the SaccadeMachine folder from your terminal (you can just write cd, press spacebar once and drag the SaccadeMachine folder into the terminal):
```cd <path to your installation folder>```

**3**- Run the software (jupyter notebook) by running the line below in the terminal:
```jupyter notebook --NotebookApp.iopub_data_rate_limit=10000000000``` 
This opens the jupyter page in your browser.

**4**- In the jupyter page on the top you should be able to see the nbextensions tab. Inside the nbextensions tab **uncheck** the option "disable configuration for nbextensions without..." from the top of the page. Also **check** the following items as well: "Table of Contents" and "CodeFolding"

**5**- Go back to the Files tab and run the SaccadeMachine notebook by clicking on the "SaccadeMachine.ipynb" file in the list and this opens the notebook in a new page.

# Running the software next times

**1**- Go to the SaccadeMachine folder from your terminal (you can just write cd, press spacebar once and drag the SaccadeMachine folder into the terminal):
```cd <path to your installation folder>```

**2**- Run the software (jupyter notebook) by running the line below in the terminal:
```jupyter notebook --NotebookApp.iopub_data_rate_limit=10000000000```
This opens the jupyter page in your browser.

**3**- Run the SaccadeMachine notebook by clicking on the "SaccadeMachine.ipynb" file in the list and this opens the notebook in a new page.

# How to close the software when you are done
Close the jupyter pages in your browser and close the terminal.

# License
This program is free software: you can redistribute it and/or modify
it under the terms of the GNU General Public License as published by
the Free Software Foundation, either version 3 of the License, or
(at your option) any later version.
This program is distributed in the hope that it will be useful,
but WITHOUT ANY WARRANTY; without even the implied warranty of
MERCHANTABILITY or FITNESS FOR A PARTICULAR PURPOSE.  See the
GNU General Public License for more details.
You should have received a copy of the GNU General Public License
along with this program.  If not, see <http://www.gnu.org/licenses/>
