#  6T SRAM Cell – Conventional vs Stacked | LTspice Simulation

##  INTRODUCTION
The 6T SRAM (Static Random Access Memory) cell is a fundamental building block in VLSI memory design, used for high-speed data storage. It consists of six transistors—four forming two cross-coupled inverters and two NMOS access transistors that interface with bitlines during read/write operations.

As CMOS size reduces, leakage power becomes a major concern. To reduce this leakage, **transistor stacking** techniques are introduced where additional series-connected transistors help lower subthreshold conduction.

### This project focuses on:
- Designing and simulating conventional and stacked 6T SRAM cells using LTspice  
- Analyzing read, write, and hold operations  
- Measuring and comparing average power consumption  
- Observing how stacking improves low-power performance  

---

##  CIRCUIT DIAGRAM

###  Fig 1 – Conventional 6T SRAM Cell  
<img width="1099" height="551" alt="image" src="https://github.com/user-attachments/assets/cce9b920-4603-4446-bd73-b4dc8101ea91" />


The conventional circuit uses six transistors to store a single bit.

###  Fig 2 – Stacked 6T SRAM Cell  
<img width="1095" height="508" alt="image" src="https://github.com/user-attachments/assets/6bdb6e26-880c-4bda-8d58-0cf24b5d032a" />


The stacked design adds four additional NMOS transistors to reduce leakage.

---

##  WORKING

###  Conventional 6T SRAM Cell
The cell consists of two CMOS inverters forming a bistable latch and two NMOS access transistors enabling connection to bitlines BL and BLB via the word-line WL.

#### Write Operation:
- WL = HIGH turns on access transistors  
- BL/BLB drive data into the cell  
- Stored state at Q and Q̅ flips accordingly  

#### Read Operation:
- WL = HIGH  
- Bitlines precharged  
- Stored data causes slight discharge on one bitline  

#### Hold Operation:
- WL = LOW  
- Cell isolated  
- Cross-coupled inverters retain data with minimal leakage  

---

###  Stacked 6T SRAM Cell
The stacked version introduces two series-connected NMOS transistors in each pull-down path of the CMOS inverters.

#### Key Advantages:
- Reduced subthreshold leakage  
- Higher effective channel resistance  
- Better hold-mode power savings  

#### Write Operation:
Similar to conventional 6T SRAM but with slightly reduced speed due to increased resistance.

#### Read Operation:
Improved stability due to controlled discharge paths.

#### Hold Operation:
Leakage dramatically reduced due to transistor stacking effect.

---

##  RESULT ANALYSIS
LTspice XVII was used to design, simulate, and analyze both SRAM cell designs.

### Tools Used:
1. LTspice XVII  
2. NMOS/PMOS transistor models  
3. Transient and power analysis tools  
4. Waveform viewer  

---

##  PROCEDURE

### 1️ Circuit Design Setup
- Create two schematics: conventional and stacked 6T SRAM  
- Use ideal NMOS/PMOS transistor models  
- Apply VDD = 1.8V  
- Define BL, BLB, and WL sources  

### 2️ Simulating Conventional 6T SRAM
- WL = HIGH for read/write  
- WL = LOW for hold  
- Perform transient analysis  
- Record power consumption and node voltages  

### 3️ Simulating Stacked 6T SRAM
- Add series NMOS transistors in inverter pull-down paths  
- Run same transient test conditions  
- Compare switching behavior and average power  

---

##  LOW POWER TECHNIQUE
The **transistor stacking effect** reduces leakage currents by:

- Increasing effective threshold voltage  
- Raising intermediate node voltage  
- Reducing Vgs and Vds  
- Minimizing subthreshold conduction paths  

Ideal for ultra-low-power memory applications.

---

##  RESULTS AND OUTPUT ANALYSIS

###  Fig 8 – Conventional 6T SRAM Output  
<img width="1075" height="662" alt="image" src="https://github.com/user-attachments/assets/53cfe67b-a21b-404a-a0b9-76cdab6b9b8d" />

Displays transient read operation and higher power consumption.

---

###  Fig 9 – Stacked 6T SRAM Output  
<img width="1078" height="544" alt="image" src="https://github.com/user-attachments/assets/79c6a225-d9fd-484a-8605-30d96c17d3b4" />


Shows reduced leakage and efficient operation with minimal power.

---

###  Power Comparison Table

| Design Type         | Average Power (pW) | Observation                    |
|---------------------|--------------------|--------------------------------|
| Conventional 6T SRAM | 37.925 pW          | Higher power dissipation       |
| Stacked 6T SRAM      | 7.0259 pW          | Reduced leakage & dynamic power |

---

##  CONCLUSION
Both **Conventional and Stacked 6T SRAM Cells** were designed and simulated successfully in LTspice under GPDK 90nm.

### Key Outcomes:
- Stacked 6T SRAM reduces power by **30–40%**  
- Maintains correct read/write/hold functionality  
- Demonstrates excellent leakage suppression  
- Ideal for low-power embedded and IoT systems  

This experiment strengthened understanding of SRAM operation, transient behavior, and low-power VLSI techniques.

---

##  REFERENCES
1. R. Jacob Baker, *CMOS: Circuit Design, Layout, Simulation*, Wiley, 2010  
2. N. Weste & D. Harris, *CMOS VLSI Design*, Pearson, 2011  
3. K. Roy et al., IEEE – Leakage Reduction Techniques, 2003  
4. S. Mutoh et al., IEEE JSSC, 1995  
5. GPDK 90nm CMOS PDK Documentation  
6. LTspice XVII User Guide – Analog Devices  

