Compilation Steps

    Download the source code and compilation files:

Download Zip
Download Tar.gz

Basic Compilation Command: Use Nuitka to compile the Python script into a standalone executable:

nuitka --onefile --windows-icon-from-ico=ico/ADCIcon.ico "ADC Archiver 1.2.0.py"

This command generates an executable in the current directory.

Including Additional Files: If the application requires additional DLLs or resources, include them using the --include-data-file option:

nuitka --onefile \
--windows-icon-from-ico=ico/ADCIcon.ico \
--include-data-file=libcrypto-3.dll=libcrypto-3.dll \
--include-data-file=tcl86t.dll=tcl86t.dll \
"ADC Archiver 1.2.0.py"

Advanced Compilation Options

Optimizing for Performance: Enable link-time optimization and follow all imports:

nuitka --onefile --lto --follow-imports "ADC Archiver 1.2.0.py"

Using ccache for Faster Builds: Configure your environment to use ccache:

set PATH=C:\path\to\ccache;%PATH%  # On Windows
export PATH=/path/to/ccache:$PATH  # On Linux

Packaging and Distribution

After successful compilation, test the executable to ensure it functions correctly:

./ADC_Archiver_1.2.0.exe

To distribute the application, consider creating an installer using tools like NSIS or Inno Setup
