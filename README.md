# sky130A-cmos-inv
CMOS Inverter Design using SKY130A PDK with Xschem, ngspice, and Magic VLSI.
# 1. Project Overview

This project focuses on the design and physical implementation of a CMOS inverter using the SKY130A Process Design Kit (PDK) and open-source VLSI tools.

The CMOS inverter is designed using Xschem, where PMOS and NMOS transistors are connected to implement the NOT logic operation. The schematic is used to generate a SPICE netlist, and ngspice is used to simulate the circuit and study its electrical behaviour.

The physical layout is developed using Magic VLSI with the SKY130A technology. Design Rule Check (DRC) is performed to identify layout rule violations, and Layout Versus Schematic (LVS) verification using Netgen is planned to check whether the physical layout matches the original schematic.

The main objective of this project is to understand the complete custom IC design flow, from schematic creation and circuit simulation to physical layout and verification using open-source EDA tools.

# 2.Objectives

- Understand the SKY130A PDK and the basic operation of a CMOS inverter.
- Set up and use open-source EDA tools for VLSI design.
- Create a CMOS inverter schematic using Xschem.
- Simulate the inverter circuit using ngspice and observe the input and output waveforms.
- Understand the physical layout of PMOS and NMOS transistors using Magic VLSI.
- Learn how to connect the input, output, power supply, and ground terminals in the layout.
- Perform Design Rule Check (DRC) to identify layout rule violations.
- Perform Layout Versus Schematic (LVS) verification to compare the physical layout with the schematic.
- Develop practical knowledge of the CMOS inverter design and physical verification flow.
 # 3. Tools and Environment

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
  # 4. Getting the Tools

To work with the SKY130A PDK and understand the CMOS inverter design flow, the following open-source EDA tools are required.

# 4.1 Magic VLSI

Magic is an open-source VLSI layout editor used to create and verify physical layouts.

Installation commands:

git clone git://opencircuitdesign.com/magic
cd magic
./configure
make
sudo make install

# 4.2 Netgen

Netgen is used to compare circuit netlists for Layout Versus Schematic (LVS) verification.

Installation commands:

git clone git://opencircuitdesign.com/netgen
cd netgen
./configure
make
sudo make install

 # 4.3 Xschem

Xschem is a schematic capture tool used to draw circuits and generate SPICE netlists.

Installation commands:

git clone https://github.com/StefanSchippers/xschem.git
cd xschem
./configure
make
sudo make install

# 4.4 ngspice

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

# 4.5 SKY130A Open-Source PDK

The SKY130A PDK provides transistor models, technology files, and design rules required for CMOS circuit design.

The PDK can be obtained from the official repository:

- "SkyWater SKY130 PDK" (https://github.com/google/skywater-pdk)
- "Open_PDKs repository" (https://github.com/RTimothyEdwards/open_pdks)

Installed PDK location:

/usr/local/share/pdk/sky130A

The PDK installation and configuration depend on the selected installation method and system setup.

# 4.6 Design Flow

1. Create the CMOS inverter schematic in Xschem.
2. Generate the SPICE netlist.
3. Simulate the circuit using ngspice.
4. Observe the input and output waveforms.
5. Create the physical layout in Magic.
6. Perform DRC to check design-rule violations.
7. Extract the layout netlist and perform LVS using Netgen.

# CMOS Inverter Schematic in Xschem

The CMOS inverter schematic was designed using **Xschem**, an open-source schematic capture tool, with the **SKY130A PDK**.

The circuit consists of two MOSFET transistors:

 **PMOS (M1):** Connected to the VDD supply.
 **NMOS (M2):** Connected to the VSS (ground) supply.
 **Input (IN):** Connected to the gates of both transistors.
 **Output (OUT):** Taken from the common connection of the PMOS and NMOS drains.

# Schematic Design

<img width="1920" height="1080" alt="Screenshot 2026-10-29 153559" src="https://github.com/user-attachments/assets/3f68b3ca-e706-429c-b2d9-d6206401b8c5" />
# Symbol Creation in Xschem

A custom symbol for the CMOS inverter was created using **Xschem** based on the previously designed schematic.

The symbol represents the CMOS inverter as a single functional block, making it easier to reuse the circuit in the testbench for simulation.
# Symbol 
<img width="1920" height="1080" alt="Screenshot 2026-10-29 154710" src="https://github.com/user-attachments/assets/83e1eecd-dd51-4ff1-8ad3-9d6c71d653d4" />
# CMOS Inverter Testbench in Xschem

The CMOS inverter testbench was created using **Xschem** to verify the functionality of the designed CMOS inverter.

The testbench uses a 1.8 V DC supply for powering the inverter and an input voltage source to apply the input signal.
# Testbench 

<img width="1920" height="1080" alt="Screenshot 2026-10-29 165942" src="https://github.com/user-attachments/assets/ff7cea60-9c02-4a20-87eb-b1d1a59ef84b" />
# 5. CMOS Inverter Simulation Results

The CMOS inverter simulation is performed using **ngspice** to analyze the circuit behaviour and verify the NOT logic operation.

The testbench applies an input voltage signal to the CMOS inverter, and the output response is observed to verify the inversion operation.


# Simulation Waveform
<img width="1920" height="1080" alt="Screenshot 2026-10-29 213520" src="https://github.com/user-attachments/assets/d9cf9628-6eae-40b5-922f-43311a243452" />




