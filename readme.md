# ADC compile from scratch

![GitHub license](https://img.shields.io/github/license/Mealman1551/ADC)
![GitHub repo size](https://img.shields.io/github/repo-size/Mealman1551/ADC)
![GitHub issues](https://img.shields.io/github/issues/Mealman1551/ADC)
![GitHub stars](https://img.shields.io/github/stars/Mealman1551/ADC)

Welcome to the **ADC-compile-from-scratch** repository! This repository provides all necessary files to manually compile the ADC Archiver 1.2.0 executable without relying on precompiled setups.

## Overview

This repository contains the source code and resources required to compile the ADC Archiver 1.2.0 from scratch. It is intended for users who prefer to build the software manually.

**Please Note:**
- This repository does not include precompiled executables or installers. It is solely intended for manual compilation using the provided source files.

## Prerequisites

Before starting the compilation process, ensure you have the following installed:

- **Python 3.12.x**: Download from the [official Python website](https://www.python.org/downloads/).
- **Nuitka**: A Python-to-C compiler. Install using:
  ```sh
  pip install nuitka
  ```
- **C/C++ Compiler** _Not required_:

_Microsoft Build Tools setup is in the main folder._
  - **Windows**: [Microsoft Build Tools](https://visualstudio.microsoft.com/visual-cpp-build-tools/) or [MinGW](https://www.mingw-w64.org/).
  - **Linux**: GCC (`sudo apt install build-essential`).
- **SCons**: A software construction tool. Install using:
  ```sh
  pip install scons
  ```
- **ccache** (optional): For caching compiled files to speed up subsequent builds.

Please note, the Python 3.12.9 setups for 64 bit as 32 bit are in the main folder, you can use these to install Python

## Project Structure

The repository includes the following key files and directories:

- `ADC Archiver 1.2.0.py`: Main Python source code.
- `ico/`: Directory containing icon files.
- `setup/`: Directory with setup-related scripts and configurations.
- `static_src/`: Directory containing static source files.
- Additional resource directories: `banner/`, `jpg/`, `png/`, `svg/`, `webp/`.

## Setting Up the Environment

1. **Install Required Libraries**:
   Ensure `nuitka` and `scons` are installed:
   ```sh
   pip install nuitka scons
   ```

2. **Verify Compiler Setup** _Not required_:
   Confirm that your C/C++ compiler is correctly installed and accessible in your system's PATH:
   ```sh
   gcc --version
   ```
   If using `ccache`, verify its installation:
   ```sh
   ccache --version
   ```

## Compilation Steps

1. **Download the source code and compilation files**:

### [Download Zip](https://github.com/Mealman1551/ADC-compile-from-scratch/archive/refs/tags/sourcecode10.zip)

### [Download Tar.gz](https://github.com/Mealman1551/ADC-compile-from-scratch/archive/refs/tags/sourcecode10.tar.gz)


2. **Basic Compilation Command**:
   Use Nuitka to compile the Python script into a standalone executable:
   ```sh
   nuitka --onefile --windows-icon-from-ico=ico/ADCIcon.ico --enable-plugin=tk-inter "ADC Archiver 1.2.0.py"
   ```
   This command generates an executable in the current directory.

3. **Including Additional Files**:
   If you want a complete portable exe, you can use the `--include-data-file` option:
   ```sh
   nuitka --onefile \
   --windows-icon-from-ico=ico/ADCIcon.ico \
   --include-data-file=libcrypto-3.dll=libcrypto-3.dll \
   --include-data-file=tcl86t.dll=tcl86t.dll \
   "ADC Archiver 1.2.0.py"
   ```

## Advanced Compilation Options

- **Optimizing for Performance**:
  Enable link-time optimization and follow all imports:
  ```sh
  nuitka --onefile --lto --follow-imports "ADC Archiver 1.2.0.py"
  ```

- **Using ccache for Faster Builds**:
  Configure your environment to use `ccache`:
  ```sh
  set PATH=C:\path\to\ccache;%PATH%  # On Windows
  export PATH=/path/to/ccache:$PATH  # On Linux
  ```

## Packaging and Distribution

After successful compilation, test the executable to ensure it functions correctly:
```sh
./ADC_Archiver_1.2.0.exe
```
To distribute the application, consider creating an installer using tools like [NSIS](https://nsis.sourceforge.io/) or [Inno Setup](https://jrsoftware.org/isinfo.php)

There is a full setup license in rtf format in the main folder called `License for setup 1.1.0.rtf` please make sure to fill in the empty spaces with your dev name etc

## Troubleshooting

- **Missing DLLs**: Ensure all required libraries are included in the compilation command and are accessible at runtime.
- **Compilation Warnings or Errors**: Review the `scons-report.txt` file for detailed logs and address any issues as indicated.

## Additional Resources

- [Nuitka User Manual](https://nuitka.net/doc/user-manual.html)
- [SCons Documentation](https://scons.org/doc.html)
- [Python 3.12.9 Documentation](https://docs.python.org/3.12/)

For further questions or issues, please create an issue in this repository.
--
If you want to support the project please consider a small donation: <a href="https://www.paypal.com/donate/?hosted_button_id=LEE83CJJ2BEJC">
	<img src="https://centerproject.org/wp-content/uploads/2021/11/paypal-donate-button-high-quality-png-1_orig.png" alt="Donate button" width="100"/>
</a>

###### © 2025 Mealman1551
