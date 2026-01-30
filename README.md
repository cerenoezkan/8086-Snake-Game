# 🐍 Snake Game on Intel 8086 Microprocessor

This project is a hardware–software integrated implementation of the classic **Snake Game** developed using the **Intel 8086 microprocessor**.  
The game runs on real hardware logic simulated in Proteus and demonstrates low-level system design principles.

---

##  Project Objective

The main goal of this project is to design an **interactive Snake Game** using the Intel 8086 microprocessor, where:

- Snake movements are controlled via **direction buttons**
- The game is displayed on an **8x8 LED Dot Matrix**
- The score is updated and shown in real time on a **16x2 LM016L LCD**
- All peripherals are managed using **8255 PPI**

---

##  System Overview

### Hardware Components
- **Intel 8086 Microprocessor**
- **8255A Programmable Peripheral Interface**
- **74LS373 Address Latch**
- **8x8 LED Dot Matrix Display**
- **LM016L 16x2 LCD**
- **Direction Buttons (UP, DOWN, LEFT, RIGHT)**

### Software Tools
- **8086 Assembly Language**
- **EMU8086** (Assembly development & testing)
- **Proteus** (Hardware simulation)

---

##  System Architecture

The system is designed using **Memory-Mapped I/O** architecture.

- **Port A:** Shared data bus (LCD data + LED Matrix rows)
- **Port B:** LED Matrix column control
- **Port C:**  
  - PC0–PC3 → Direction buttons  
  - PC4 → LCD RS  
  - PC5 → LCD Enable  

The 8255 PPI operates in **Mode 0 (Simple I/O)**.

---

##  Project Versions

### Version 1 – I/O Verification Model
- No external RAM or ROM
- Focused on validating:
  - I/O communication
  - LCD and LED Matrix control
  - Button polling logic
- Acts as a hardware verification platform

### Version 2 – Extended Architecture
- Includes external **RAM and ROM**
- Represents a realistic **Single Board Computer (SBC)** architecture
- Implements full address decoding and memory hierarchy

---

##  Game Logic

1. **Initialization**
   - Snake starts with length 3
   - Initial score shown on LCD

2. **Input Polling**
   - Direction buttons are continuously scanned via Port C

3. **Display Update**
   - LED Matrix is driven using multiplexing technique
   - Real-time snake movement visualization

4. **Game Rules**
   - Snake grows when food is eaten
   - Score updates instantly on LCD
   - Wall wrapping is enabled
   - Self-collision ends the game

5. **Game Over**
   - "GAME OVER" message on LCD
   - LED Matrix flashes as visual feedback

---




