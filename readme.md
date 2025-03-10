# ADC compile from scratch

Welcome to the **ADC-compile-from-scratch** repository! This repository includes all the necessary files for manually compiling the full ADC 1.2.0.exe without needing to use the setup from the main branch.

### Overview

This repository contains the **Nuitka** files required to compile an EXE package from scratch. It is designed for users who want to build the software manually without relying on precompiled setups and/or precompiled executables.

**Please Note:**  
- This repository does not include the EXE files or precompiled setups. It is solely intended for compiling the software from scratch using the following resources:
    - C
    - H
    - O
    - Python files (`.py`, `.pyw`, `.pyd`)
    - DBlite/SQLite
    - BIN
    - CONST
    - TK and TCL files

### Prerequisites

Before you start compiling, you need to have the following installed:

- **Python 3.12.x** (with the Nuitka library)
- **C** (for compiling C-based files)
- **Python Tkinter** (for GUI-related tasks)
- **DBlite/SQLite** (for database operations)
- **JavaScript** (to modify certain files if needed)

### Setup

1. Install **Python 3.12.x** from the [official Python website](https://www.python.org/downloads/). (Python 3.12.x recommended)
2. Install the **Nuitka library** for Python (refer to the [Nuitka documentation](https://nuitka.readthedocs.io/) for installation steps).
3. Ensure that **C**, **Tkinter**, **DBlite/SQLite**, and **JavaScript** are installed and properly configured on your system.

### Compiling from Scratch

To compile the software manually, you will need to use the Python source code file:

- **`ADC Archiver 1.2.0.py`** (Full source code)

## Compiling instructions

**Compiling Instructions for ADC Archiver 1.2.0**

This document provides detailed instructions on how to compile ADC Archiver 1.2.0 using Nuitka, including prerequisites, step-by-step commands, troubleshooting, and advanced options.

**Table of Contents**

- 1. Prerequisites
- 2. Project Structure
- 3. Setting Up the Environment
- 4. Compilation Steps
- 5. Advanced Compilation Options
- 6. Packaging and Distribution
- 7. Troubleshooting
- 8. Download of source code and files
- 9. Additional Resources

**1. Prerequisites**

**1.1 Software Requirements**

- **Python 3.12.x**
- **Nuitka** (`pip install nuitka`)
- **C/C++ Compiler**
  - **Windows**: Microsoft Build Tools or MinGW
  - **Linux**: GCC (`sudo apt install build-essential`)
- **SCons** (`pip install scons`)
- **ccache** (optional, for caching compiled files)

**2. System Requirements**

- Minimum 4 GB RAM (8 GB Recommended)
- Sufficient disk space for temporary compilation files

**3. Setting Up the Environment**

**3.1 Install Required Libraries**

`pip install nuitka scons`

**3.2 Verify Compiler Setup**

`gcc --version`

`ccache --version`

Ensure all compilers are in your PATH.

**4. Compilation Steps**

**4.1 Basic Compilation Command**

`nuitka --onefile --windows-icon-from-ico=ico\ADCIcon.ico "ADC Archiver 1.2.0.py"`

**4.2 Including Additional Files**

`nuitka --onefile \

\--windows-icon-from-ico=ico\ADCIcon.ico \

\--include-data-file=libcrypto-3.dll=libcrypto-3.dll \

\--include-data-file=tcl86t.dll=tcl86t.dll \

"ADC Archiver 1.2.0.py"`

**5. Advanced Compilation Options**

**5.1 Optimizing for Performance**

`nuitka --onefile --lto --follow-imports "ADC Archiver 1.2.0.py"`

**5.2 Using Ccache for Faster Builds**

`set PATH=C:\path\to\ccache;%PATH%`

**6. Packaging and Distribution**

**6.1 Testing the Executable**

`ADC Archiver 1.2.0.exe`

**6.2 Creating an Installer**

You can use NSIS, Inno Setup, or InstallForge to create a setup wizard.

**7. Troubleshooting**

**7.1 Common Errors**

- **Missing DLLs**: Verify that all required libraries are in the correct directories.
- **Compilation Warnings**: Check scons-report.txt for detailed logs.

**8 Download**

## [Download Zip](https://github.com/Mealman1551/ADC-compile-from-scratch/archive/refs/tags/sourcecode.zip)

## [Download Tar.gz](https://github.com/Mealman1551/ADC-compile-from-scratch/archive/refs/tags/sourcecode.tar.gz)

**9. Additional Resources**

- [Nuitka Documentation](https://nuitka.net/user-documentation/)
- [SCons Documentation](https://scons.org/documentation.html)
- [Python 3.12 Downloads](https://www.python.org/downloads/release/python-3129/)
- [Tcl/TK Documentation](https://www.tcl-lang.org/doc/)

For any further questions or issues, you can create an issue on this repo!

(c) 2025 Mealman1551
