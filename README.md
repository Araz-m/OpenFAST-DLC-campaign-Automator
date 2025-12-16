# OpenFAST-DLC-campaign-Automator

A Python tool for **automating sequential execution of multiple OpenFAST DLC simulations** across different design load cases (DLCs). 

This program is designed to complement the [OpenFAST-DLC-sampler-Automator](https://github.com/Araz-m/OpenFAST-DLC-sampler-Automator), which handles running individual DLC simulations. When multiple DLCs need to be executed consecutively, this tool allows the entire campaign to run **unattended**, without requiring the user to manually start each DLC.

---

## Motivation

In typical OpenFAST workflows:

- Each DLC may contain **tens of simulations**, and each DLC simulation can take several hours to complete.  
- Running multiple DLCs sequentially manually is **time-consuming** and requires constant monitoring.  

This tool automates the process, allowing Different DLC simulations to execute sequentially, freeing the user from continuous supervision.

---

## Features

- Sequentially executes multiple DLC automation scripts in their respective directories  
- Streams standard output and errors in real time  
- Automatically starts the next DLC when the previous one finishes  
- Reduces manual effort in long-running simulation campaigns  

**Note:** This tool does **not** run simulations in parallel and does not modify OpenFAST input files.

---

## How It Works

The main script (`FullyAutomate.py`) contains a predefined list of:

- DLC script filenames (e.g., `DLC51.py`, `DLC61.py`)  
- Corresponding directories where each script is located  

Each DLC script can be generated and executed independently using the OpenFAST-DLC-sampler-Automator. The campaign automator ensures these DLC scripts are executed **in sequence** without user intervention.

---

## Requirements

- Python 3.x  
- OpenFAST installed and configured  
- DLC automation scripts (e.g., generated with [OpenFAST-DLC-sampler-Automator](https://github.com/Araz-m/OpenFAST-DLC-sampler-Automator))  
- Windows environment (paths currently hard-coded)  

---

## Usage

1. Place a DLC automation script in each DLC directory.  
2. Rename each script according to its corresponding DLC.  
3. Update the paths in `FullyAutomate.py` to point to each DLC script directory.  
4. Run the campaign




For detailed information on setup steps, please refer to the [OpenFAST-DLC-sampler-Automator
](https://github.com/Araz-m/OpenFAST-DLC-sampler-Automator/tree/main).
