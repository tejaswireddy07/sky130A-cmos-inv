# sky130A-cmos-inv
CMOS Inverter Design using SKY130A PDK with Xschem, ngspice, and Magic VLSI.

1. Project Overview

This project focuses on the design and physical verification of a CMOS inverter using the open-source SKY130A Process Design Kit (PDK). The main objective is to understand the complete VLSI design flow, starting from schematic creation and circuit simulation to physical layout design and verification.

The CMOS inverter schematic is created using Xschem, and its electrical behavior is simulated using ngspice. The simulation waveform is used to verify the inverter's NOT-gate operation, in which the output voltage is the logical complement of the input voltage.

The physical layout is developed using Magic VLSI with the SKY130A technology. Design Rule Check (DRC) and Layout Versus Schematic (LVS) verification are planned to check the layout against the technology rules and the original schematic.

This project provides practical experience with open-source EDA tools and helps build a foundation in VLSI circuit design, layout development, and physical verification.
2. Objectives

- Understand the SKY130A PDK and the basic operation of a CMOS inverter.
- Set up and use open-source EDA tools for VLSI design.
- Create a CMOS inverter schematic using Xschem.
- Simulate the inverter circuit using ngspice and observe the input and output waveforms.
- Understand the physical layout of PMOS and NMOS transistors using Magic VLSI.
- Learn how to connect the input, output, power supply, and ground terminals in the layout.
- Perform Design Rule Check (DRC) to identify layout rule violations.
- Perform Layout Versus Schematic (LVS) verification to compare the physical layout with the schematic.
- Develop practical knowledge of the CMOS inverter design and physical verification flow.
3. Tools and Environment

The following tools and technologies are used in this project:

- Operating System: Ubuntu on Windows Subsystem for Linux (WSL) — provides the Linux environment for running VLSI tools.
- Process Design Kit (PDK): SKY130A PDK — provides technology files, transistor models, and design rules.
- Schematic Editor: Xschem — used to create the CMOS inverter schematic and testbench.
- Circuit Simulator: ngspice 47 — used to simulate the inverter circuit and observe input and output waveforms.
- Layout Editor: Magic VLSI — used to view and develop the physical layout of the CMOS inverter.
- LVS Verification Tool: Netgen — used to compare the schematic netlist with the extracted layout netlist.

Technology and Installation Path

- Technology: SkyWater SKY130A
- PDK Installation Path: "/usr/local/share/pdk/sky130A"
- Schematic Design: Xschem
- Circuit Simulation: ngspice 47
- Physical Layout Design: Magic VLSI
- Verification: DRC using Magic and LVS using Netgen
4. Getting the Tools

To work with the SKY130A PDK and understand the CMOS inverter design flow, the following open-source EDA tools are required.

4.1 Magic VLSI

Magic is an open-source VLSI layout editor used to create and verify physical layouts.

Installation commands:

git clone git://opencircuitdesign.com/magic
cd magic
./configure
make
sudo make install

4.2 Netgen

Netgen is used to compare circuit netlists for Layout Versus Schematic (LVS) verification.

Installation commands:

git clone git://opencircuitdesign.com/netgen
cd netgen
./configure
make
sudo make install

4.3 Xschem

Xschem is a schematic capture tool used to draw circuits and generate SPICE netlists.

Installation commands:

git clone https://github.com/StefanSchippers/xschem.git
cd xschem
./configure
make
sudo make install

4.4 ngspice

ngspice is an open-source circuit simulator used to simulate the CMOS inverter and observe its input and output waveforms.

Installation commands used for the source build:

tar -xzvf ngspice-47.tar.gz
cd ngspice-47
mkdir release
cd release
../configure --with-x --with-readline=yes --disable-debug
make -j2
make install

Note: In this project, ngspice 47 was installed under the user's home directory using the prefix "$HOME/ngspice47-install". The commands above show the main build steps; the configure command must include the same installation prefix when reproducing this setup.

4.5 SKY130A Open-Source PDK

The SKY130A PDK provides transistor models, technology files, and design rules required for CMOS circuit design.

The PDK can be obtained from the official repository:

- "SkyWater SKY130 PDK" (https://github.com/google/skywater-pdk)
- "Open_PDKs repository" (https://github.com/RTimothyEdwards/open_pdks)

Installed PDK location:

/usr/local/share/pdk/sky130A

The PDK installation and configuration depend on the selected installation method and system setup.

4.6 Design Flow

1. Create the CMOS inverter schematic in Xschem.
2. Generate the SPICE netlist.
3. Simulate the circuit using ngspice.
4. Observe the input and output waveforms.
5. Create the physical layout in Magic.
6. Perform DRC to check design-rule violations.
7. Extract the layout netlist and perform LVS using Netgen.
