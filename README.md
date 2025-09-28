# ADC compile from source

![GitHub license](https://img.shields.io/github/license/Mealman1551/ADC)
![GitHub repo size](https://img.shields.io/github/repo-size/Mealman1551/ADC)
![GitHub issues](https://img.shields.io/github/issues/Mealman1551/ADC)
![GitHub stars](https://img.shields.io/github/stars/Mealman1551/ADC)

Welcome to the **ADC-compile-from-source** repository! This repository provides all necessary files to manually compile the ADC Archiver 1.3.0 executable without relying on precompiled setups.

## Overview

This repository contains the source code and resources required to compile the ADC Archiver 1.3.0 from scratch. It is intended for users who prefer to build the software manually.


## Windows

1. Install Python 3.12.x, you can download it [here](https://www.python.org/ftp/python/3.12.10/python-3.12.10-amd64.exe) (64bit only)


**please note:** Python 3.12.10 setups for both 64 and 32 bits are in the source package that you will be downloading in the next steps.


2. Add Python to path while installing.
3. Download the source archive, for Windows this will be a zip archive: [Download source package for Windows](https://github.com/Mealman1551/ADC-compile-from-scratch/archive/refs/tags/sourcecode16.zip)
4. Extract the zip.
5. Open the terminal in the source archive.
6. Install required Python libraries with:
```powershell
pip install -r requirements.txt
```
7. Install Nuitka and Scons:
```powershell
pip install nuitka scons
```
### Compile on Windows

1. Run in the terminal, cd'ed in the source archive:
```powershell
nuitka --standalone --enable-plugin=tk-inter "ADC_Archiver_1.3.0.py"
```
2. After compiling is done, open the `dist` folder, there you will see: `ADC_Archiver_1.3.0.exe`
3. Run the executable by dubble clicking the file or:
```powershell
./ADC_Archiver_1.3.0.exe
```

For custom .exe icon please use ResourceHacker as Nuitka doesnt support icons anymore.

## Linux

Python is almost everywhere pre-delivered on most Linux distro's

1. Download the source archive for Linux [Download source package for Linux](https://github.com/Mealman1551/ADC-compile-from-scratch/archive/refs/tags/sourcecode16.tar.gz)
2. Open the terminal in the source archive.
3. Install required Python libraries:
```sh
pip install -r requirements.txt
```
4. Install Nuitka and Scons:
```sh
pip install nuitka scons
```
5. Install Tkinter
```sh
sudo apt install python3-tk
```
6. Install Patchelf:
```sh
sudo apt install patchelf
```
7. Optional: Install ccache to make compiling faster:
```sh
sudo apt install ccache
```

### Compile on Linux

1. Compile with:
```sh
nuitka --standalone --enable-plugin=tk-inter "ADC_Archiver_1.3.0.py"
```
2. After compiling you can open the executable by running:
```sh
./ADC_Archiver_1.3.0.bin
```

---

## Using Python 3.13 and up

Python 3.13 and up compilation works on Linux but for Windows you need a C compiler, in the source archive there is a file named `vs_BuildTools.exe`, run this on Windows and now you will be able to compile on Python 3.13 and up on Windows.

> [!Note]
> Im currently testing if MinGW64 is also possible.

## Project Structure

The repository includes the following key files and directories:

- `ADC_Archiver_1.3.0.py`: Main Python source code.
- `ico/`: Directory containing icon files.
- `setup/`: Directory with setup-related images like the `setupbox.ico`.
- Additional resource directories: `banner/`, `jpg/`, `png/`, `svg/`, `webp/`.
- `get-pip.py` is the script to install pip (If not already delivered with your Python installation).
- `License for setup 1.1.rtf` The documents for distributing setup.exe's.
- `LICENSE` Is the License (GPLv3 license) file.
- `python-3.12.10-32bit.exe` and `python-3.12.10-amd64.exe` Are the setup files for Python on both 64 as 32 bit Python.
- `requirements.txt` Includes Python libraries needed for ADC to work.
- `runtime.txt` Is the file that tells which Python versions are compatible.
- `vs_BuildTools.exe` The setup for MSVC (Clang compiler) to compile on Python 3.13.x.

## Advanced Compilation Options

- **Optimizing for Performance**:
  Enable link-time optimization and follow all imports:
  ```sh
  nuitka --standalone --lto --follow-imports "ADC_Archiver_1.3.0.py"
  ```

- **Using ccache for Faster Builds**:
  Configure your environment to use `ccache`:
  ```sh
  export PATH=/path/to/ccache:$PATH
  ```

## Packaging and Distribution

After successful compilation, test the executable to ensure it functions correctly:
```sh
./ADC_Archiver_1.3.0.bin
```
``` powershell
./ADC_Archiver_1.3.0.exe
```

To distribute the application, consider creating an installer using tools like [NSIS](https://nsis.sourceforge.io/) or [Inno Setup](https://jrsoftware.org/isinfo.php) (for Windows), or packaging for Linux using tools like `dpkg` or `rpm`.

There is a full setup license in RTF format in the source archive called `License for setup 1.1.0.rtf`. Please make sure to fill in the empty spaces with your dev name, etc.

## Troubleshooting

- **Missing DLLs or SOs**: Ensure all required libraries are included in the compilation command and are accessible at runtime.
- **Compilation Warnings or Errors**: Review the `scons-report.txt` file for detailed logs and address any issues as indicated.

## Additional Resources

- [Nuitka User Manual](https://nuitka.net/doc/user-manual.html)
- [SCons Documentation](https://scons.org/doc.html)
- [Python 3.12.10 Documentation](https://docs.python.org/3.12/)

For further questions or issues, please create an issue in this repository.

---

If you want to support the project please consider a small donation: <a href="https://www.paypal.com/donate/?hosted_button_id=LEE83CJJ2BEJC">
	<img src="https://centerproject.org/wp-content/uploads/2021/11/paypal-donate-button-high-quality-png-1_orig.png" alt="Donate button" width="100"/>
</a>

###### © 2025 Mealman1551
