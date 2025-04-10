# Nanolib

![Image](https://www.motioncontroltips.com/wp-content/uploads/2016/04/Kollmorgen-Stepper-cutaway.jpg)

This is the Python version of NanoLib with an example application. <br>
The NanoLib offers an easy to use library to control Nanotec devices.

**[www.nanotec.de](https://www.nanotec.de/)** 

**[NanoLib Python User Manual V1.3.0](https://rock-technologies.com/Downloads/ABW/Simplenotes/NanoLib-Python_User_Manual_V1.3.0.pdf)**

## Example Application
### Overview and Structure
The CLI example application provides a menu interface where the user can execute
the different library functions. 

The menu offers the user the possibility toeasily and quickly select and execute all functions supported by NanoLib.
The menu entries are context based and will be enabled or disabled, depending on
the state.

To enable all entries you have to:

1. Scan for hardware buses
2. Connect to a found harwdare bus
3. Scan for devices on the opened hardware bus
4. Successfully connect to a found device<br>
 
With this example application it is possible to:<br> 
- do a hardware bus scan
- open a found bus hardware (several hardware buses allowed)
- close an opened bus hardware
- scan for devices on opened hardware bus(es)
- connect to a found device (several devices allowed)
- disconnect from a connected device 
- read device informations
- update the firmware
- update the bootloader
- upload a NanoJ program
- run/stop a NanoJ program
- reboot a device
- set logging and logging callback parameters
- auto tune a motor (may require manual steps before)
- get a motor to rotate
- use the object dicationary interface for reads/writes
- sample data
- scan for Profinet devices
- etc.

The application menu and the supported NanoLib functionality is logically structered into several files:

Files with **\*_functions_example.py** contain the implementations for the NanoLib interface functions.

Files with **\*_callback_example.py** contain implementations for the various callbacks (scan, data and logging).

Files with **menu\_\*.py** contain the menu logic and code.

**Example.py** is the main program, creating the menu and initializing all used parameters.

**Sampler_example.py** contains the example implementation for sampler usage.

### Linux Installation
#### Prerequisites
- A python 3.7 up to python 3.12 installation is required. We highly recommend the official version <br>
  from [python.org](https://www.python.org/downloads/).<br>
- We recommend using a virtual environment before installing NanoLib:
1. Open a command prompt (e.g. powershell) and use the following commands to setup a virtual environment:
   ```bash
   cd <nanolib_directoy>
   python3 -m venv .venv
   source .venv/bin/activate
   ```
   **_Note:_** Depending on the used Python version, the names and location of the activation script may differ.<br>
   
   In case the setup was successful the CMD is prefixed with `(.venv)`.<br>
   
2. The package 'wheel' is necessary to install NanoLib as egg:
   ```bash
   pip3 install wheel
   ```

#### Installing the NanoLib Egg 
##### Checking Your Linux Architecture
```
uname -m
lscpu
```
Look for the “Architecture” line in the output:
- If it says **x86_64**, you are on a 64-bit x86 architecture and then use **NanoLib**
- If it says **aarch64**, you are on a 64-bit ARM architecture and then use **NanoLib**

##### If x86_64
```
pip3 install https://rock-technologies.com/Downloads/ABW/NanoLib/nanolib_python_linux_1.3.0.tar.gz
```

##### If aarch64
```
pip3 install https://rock-technologies.com/Downloads/ABW/NanoLib/nanolib_python_linux_arm64_1.3.0.tar.gz
```

Wait for the console to produce a success report ending on "Successfully installed nanotec_nanolib_linux_[arm64_]N.N.N".<br>
**_Note:_** Where `N.N.N` is the actual version of the NanoLib. <br>

#### Check proper Installation
```bash
python3
```
- Inside the python shell import the NanoLib and press Enter:
```python
import nanotec_nanolib
```
If no error shows, the installation was successful.<br>
You can now leave Python by typing exit() and press Enter.<br>

#### Running the example project
```bash
python3 example.py
```
