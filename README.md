# 0.C. Installing XCrySDen

## Theory

`XCrySDen` is a graphical visualization program commonly used with Quantum ESPRESSO and other electronic-structure codes. It is used to visualize crystal structures, atomic positions, unit cells, and Quantum ESPRESSO input/output files.

## Procedure

- Update the package list:
  
    ```bash
    sudo apt update


- Install XCrySDen:

   ```bash
    sudo apt install xcrysden

- Check whether XCrySDen has been installed correctly:
  
  ```bash
    which xcrysden


- Start XCrySDen:
```bash
    xcrysden
```
- If XCrySDen opens normally, congratulations!!!

- If XCrySDen does not open or gives an OpenGL/ToGL error

- Create the XCrySDen configuration directory:
```bash
    mkdir -p ~/.xcrysden
```
- Copy the default `custom-definitions` file to the user configuration directory:
```bash
    cp /usr/share/xcrysden/Tcl/custom-definitions ~/.xcrysden/
```
- Open the copied file:
```bash
    nano ~/.xcrysden/custom-definitions
```
- Find the following line:

    #set toglOpt(accum) false

- Remove `#` from the beginning so that it becomes:

  set toglOpt(accum) false

- Save and exit:

    Ctrl + O
    Enter
    Ctrl + X

- Start XCrySDen again:
```bash
    xcrysden
```
- To open a Quantum ESPRESSO input file:
```bash
    xcrysden --pwi scf.in
```
- To open a Quantum ESPRESSO output file:
```bash
    xcrysden --pwo scf.out
```
- To open a CIF file:
```bash
    xcrysden --cif structure.cif
```


- **Note:** `set toglOpt(accum) false` is not required for every XCrySDen installation. It is only a troubleshooting step for OpenGL/ToGL-related startup problems.

