# 0.C. Installing XCrySDen

## Theory

`XCrySDen` is a graphical visualization program commonly used with Quantum ESPRESSO and other electronic-structure codes. It is used to visualize crystal structures, atomic positions, unit cells, and Quantum ESPRESSO input/output files. Unlike `thermo_pw`, XCrySDen is a standalone program and does not need to be compiled inside the Quantum ESPRESSO source tree. On Ubuntu, it can be installed directly using the package manager. However, on some systems XCrySDen may fail to open because of OpenGL/ToGL compatibility issues. In such cases, the `custom-definitions` file can be copied to the user's home directory and `toglopt false` can be enabled to disable the ToGL option.

## Procedure

- Update the package list:

    sudo apt update

- Install XCrySDen:

    sudo apt install xcrysden

- Check whether XCrySDen has been installed correctly:

    which xcrysden

- Start XCrySDen:

    xcrysden

- If XCrySDen opens normally, congratulations!!!

- If XCrySDen does not open or gives an OpenGL/ToGL error, first run it from the terminal and check the error message:

    xcrysden

- Create the XCrySDen configuration directory:

    mkdir -p ~/.xcrysden

- Copy the default `custom-definitions` file to the user configuration directory:

    cp /usr/share/xcrysden/Tcl/custom-definitions ~/.xcrysden/

- Open the copied file:

    nano ~/.xcrysden/custom-definitions

- Find the following line:

    # toglopt false

- Remove `#` from the beginning so that it becomes:

    toglopt false

- Save and exit:

    Ctrl + O
    Enter
    Ctrl + X

- Start XCrySDen again:

    xcrysden

- To open a Quantum ESPRESSO input file:

    xcrysden --pwi scf.in

- To open a Quantum ESPRESSO output file:

    xcrysden --pwo scf.out

- To open a CIF file:

    xcrysden --cif structure.cif

- If XCrySDen still does not open, install OpenGL utilities:

    sudo apt install mesa-utils

- Check the OpenGL configuration:

    glxinfo | grep "OpenGL"

- If using an NVIDIA GPU, check the NVIDIA driver:

    nvidia-smi

- **Note:** `toglopt false` is not required for every XCrySDen installation. It is only a troubleshooting step for OpenGL/ToGL-related startup problems.
- **Note:** Do not modify `/usr/share/xcrysden/Tcl/custom-definitions` directly. Copy it to `~/.xcrysden/` and modify the user-specific copy.
- **Note:** XCrySDen does not need to be installed inside the Quantum ESPRESSO source directory.
- **Reference:** http://www.xcrysden.org/
