# AXI4-Full Master–Slave Communication (RTL Design)

## 📌 Project Overview

This project implements a complete AXI4-Full communication system using Verilog HDL with one Master and one Slave. The design supports both read and write burst transactions and follows the standard VALID–READY handshake mechanism of the AXI protocol.

The objective of this project was to understand the AXI4 protocol in depth and implement it at RTL level with proper control logic and response handling.

---

## 🏗️ Architecture

The design consists of:

- 1 AXI4 Master
- 1 AXI4 Slave
- Five independent AXI channels:
  - Write Address Channel (AW)
  - Write Data Channel (W)
  - Write Response Channel (B)
  - Read Address Channel (AR)
  - Read Data Channel (R)

Both Master and Slave are implemented using FSM-based control logic.

---

## 🚀 Key Features

- Single Master – Single Slave architecture  
- Full AXI4-Full protocol implementation  
- Burst-based read and write transactions (INCR burst supported)  
- Proper VALID–READY handshake implementation  
- Configurable burst length (AWLEN / ARLEN)  
- Data size handling (AWSIZE / ARSIZE)  
- Correct WLAST and RLAST generation  
- Write response (BRESP) and Read response (RRESP) handling  
- Fully verified using simulation testbench  

---

## ✍️ Write Transaction Flow

1. Master sends Write Address (AW channel)
2. Master sends burst Write Data (W channel)
3. Slave sends Write Response (B channel)

Flow Sequence:
AW → W → B

---

## 📖 Read Transaction Flow

1. Master sends Read Address (AR channel)
2. Slave sends burst Read Data with response (R channel)

Flow Sequence:
AR → R

---

## 🧠 Design Methodology

- FSM-based architecture for both Master and Slave
- Burst counter logic used to manage beat transfers
- Address increment logic implemented for INCR burst
- Proper synchronization using VALID and READY handshake signals
- Response signals generated based on transaction status

---

## 🧪 Verification

The design was verified using a directed testbench.

Simulation confirms:
- Correct burst write and read operations
- Proper handshake behavior
- Correct BRESP and RRESP generation
- Accurate WLAST and RLAST signaling
- Successful completion of full AXI transactions

Waveforms were analyzed using ModelSim / Vivado simulator.

##Simulation Waveform(images/simulation_waveform.png)
---

## 🛠️ Tools Used

- Verilog HDL  
- ModelSim / Vivado Simulator  
- GitHub (Version Control)  

---

## 📚 Learning Outcomes

Through this project, I gained strong understanding of:

- AXI4-Full protocol architecture  
- Burst transaction handling  
- VALID–READY handshake mechanism  
- RTL design using Finite State Machines  
- Functional verification using simulation  

---

## 🔮 Future Improvements

- Add support for FIXED and WRAP burst types  
- Extend to Multi-Master / Multi-Slave system  
- Implement UVM-based verification  
- Add performance analysis  

