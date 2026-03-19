# Routing with CGR for IPv6
This repository contains a project that explores the capability of CGR (Contact Graph Routing) to operate with IPv6 addresses instead of its traditional implementation based on Node Identifiers.
The core of this project is a code written in C that utilizes a CGR function library implemented in Python.

## REPOSITORY STRUCTURE
```
inside py_cgr/
├── contact plans/         # .txt files with different contact plans examples
├── py_cgr_lib/            # Python CGR library
└── Prova_pk_ip.c
```

## py_cgr_lib.py
Library extracted from https://bitbucket.org/juanfraire/pycgr/src/master/. Modified to be used for IPv6 packets instead of Bundles. 

## Prova_pk_ip.c
This file contains the main c code that invokes the functions in the CGR library. It contains the logic to test route finding based on IPs and time, thus validating the hypothesis of use with IPv6.
  - Initialization: Configures the c environment for interaction with the Python library (using the Py_Initialize() function from the Python C API).
  - Packet Parameter Creation: It defines and constructs the necessary parameters to simulate an IPv6 packet. These parameters are essential input for the CGR algorithm to calculate possible routes.
  - Address Management: Translates IPv6 addresses into a format manageable for CGR.

## Compile and run
```bash     
gcc Prova_pk_ip.c -o Prova_pk_ip $(python3-config --cflags --ldflags --embed)
./Prova_pk_ip
```

## AUTHORS
Cèlia Torras Pérez celia.torras@estudiantat.upc.edu — Initial author and main developer

Anna Calveras anna.calveras@upc.edu — Project supervisor

## Funding
This work is partially supported by Spanish MCIN/AEI/ 10.13039/501100011033/FEDER/UE through project PID2023-146378NB-I00.
