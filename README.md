# 🗳️ EVM - Electronic Voting Machine
> A digital Electronic Voting Machine built using 74LS90 (Decade Counter) and 74LS47 (BCD to 7-Segment Decoder) simulated in Proteus 8 Professional.

---

## 📌 Project Overview

This project simulates a basic **Electronic Voting Machine (EVM)** where each candidate has:
- A dedicated **vote button** (push button as clock input)
- A **decade counter (74LS90)** to count votes (0–9)
- A **BCD decoder (74LS47)** to convert binary count to display format
- A **7-segment display** to show the vote count in real time

The design is modular — one unit per candidate — and can be replicated for multiple candidates.

---

## 🧰 Components Used

| Component | Part Number | Quantity | Purpose |
|-----------|-------------|----------|---------|
=> Decade Counter ( 74LS90) -> 1 per candidate -> Counts votes (0–9) 
=> BCD to 7-Seg Decoder ( 74LS47 ) -> 1 per candidate -> Decodes count to display 
=>7-Segment Display (7SEG-COM-ANODE) -> 1 per candidate -> Shows vote count 
=> Push Button ( BUTTON ) -> 1 per candidate -> Vote input / clock trigger 
=>Power Supply | VCC (+5V) ->  1 -> Powers all ICs 
=> Ground | GND | Multiple | Common ground |

---


## 🗂️ Project Structure

```
EVM-Project/
│
├── Proteus/
│   └── sample EVM.pdsprj       # Proteus 8 project file
│
├── Screenshots/
│   └── schematic.png           # Circuit schematic screenshots
│
└── README.md                   # This file
```

---

## ⚙️ How It Works

1. Each press of the **Vote Button** sends a clock pulse to **CKB (Pin 1)** of the 74LS90.
2. The 74LS90 increments its BCD count (Q0–Q3) by 1 on each falling edge.
3. The BCD output is fed into the **74LS47**, which decodes it into 7-segment signals.
4. The **7-segment display** shows the current vote count (0–9).
5. Resetting R0(1) and R0(2) to HIGH resets the counter to 0.

---

## 🔄 Replication for Multiple Candidates

To add more candidates, **duplicate the entire unit** (74LS90 + 74LS47 + 7-SEG + BUTTON) for each candidate. All units share the same VCC and GND rails.

```
Candidate 1: U2 (74LS90) + U1 (74LS47) + Display 1 + Button 1
Candidate 2: U4 (74LS90) + U3 (74LS47) + Display 2 + Button 2
Candidate 3: U6 (74LS90) + U5 (74LS47) + Display 3 + Button 3
```

---

## 🛠️ Tools Used

- **Proteus 8 Professional** — Schematic design and simulation
- **74LS TTL Logic Family** — All ICs are from the LS (Low-power Schottky) series

---

## 🚧 Current Status

- [] Single candidate unit designed
- [x] 74LS90 decade counter connected
- [x] 74LS47 BCD decoder connected
- [x] 7-segment display connected
- [x] GND terminals placed
- [ ] VCC terminals on all ICs (in progress)
- [ ] Vote button connected to CKB
- [ ] Multi-candidate replication
- [ ] Final simulation and testing

---


Done BY:
- GitHub: [@Priyadharshini](https://github.com/priyadharshinielumalai007)

