# Wiring Guide: Mesa 7i96S to 18-Wire MPG Pendant

**Project:** PrintNC CNC Build  
**Date:** March 1, 2026  
**Hardware:** Mesa 7i96S Ethernet Card + 18-Wire Chinese MPG Pendant

---


### **Mesa Jumper Configuration**
To support the differential signals (A/A- and B/B-) from the pendant:
*   Set Jumpers **W1, W2, and W3** to the **RIGHT-HAND** position (Differential Mode).

---

## 2. Isolated Inputs: Axis & Multiplier (TB3)
The switches and buttons are wired to the isolated input block. This guide assumes a standard **24V Sourcing (PNP)** setup.



### **Input Mapping**
# Mesa MPG Wiring Reference

### P1 Expansion Port
| DB25 | Mesa | MPG-wire-colour | Function |
| :--- | :--- | :--- | :--- |
| 15 | IO37 | Brown | Z Select |
| 16 | IO39 | Yellow/Black | Y Select |
| 17 | IO41 | Yellow | X Select |
| 10 | IO47 | Gray | X1 |
| 11 | IO48 | Gray/Black | X10 |
| 12 | IO49 | Orange | x100 |
| 18 | GND | Orangle/Black | switches GND (v5 gnd) |

### TB2
| Mesa | MPG-wire-colour | Function |
| :--- | :--- | :--- |
| 1 | White/Black | LED- |
| 6 | Green/Black | LED+ |
| 12 | Red | +5V |
| 9 | Black | gnd (5v gnd) |
| 7 | Green | A+ |
| 8 | Purple | A- |
| 10 | White | B+ |
| 11 | Purple/Black | B- |

### TB3
| Mesa | MPG-wire-colour | Function |
| :--- | :--- | :--- |
| IO10 | Blue/Black | E-STOP-INPUT |
| 24v-GND | Blue | E-STOP-GND |

---


## 4. Auxiliary: LED & Enable Switch
*   **Indicator LED:** 
    *   **Green/Black (LED+):** Connect to +5V or +24V.
    *   **White/Black (LED-):** Connect to Ground.
*   **Enable/Deadman Switch:** This is the button on the side of the pendant. 
    *   **Identification:** Use a multimeter to check for continuity between **Orange/Black (COM)** and the **Brown/Black** wire while the side button is pressed.
    *   **Mesa Pin:** Connect the identified wire to **TB3 Pin 8 (Input 7)**.

---

## 5. Chinese Label Translation Table
| Chinese Label | English Translation |
| :--- | :--- |
| **轴选** (Zhóu xuǎn) | Axis Selection |
| **倍率** (Bèilǜ) | Multiplier (X1, X10, X100) |
| **急停** (Jí tíng) | Emergency Stop |
| **指示灯** (Zhǐshì dēng) | Indicator LED |
| **脉冲发生器** (Màichōng fāshēng qì) | Pulse Generator (MPG Wheel) |
| **COM** | Switch Common (Return Path) |

---

### **Pre-Power Validation**
Before turning on the machine:
1.  Check that the Red/Black power wires are not swapped.
2.  Verify that turning the Axis knob sends +24V to the expected Mesa Input pin.
3.  Ensure the E-Stop shows as "Closed" (high signal) when not pressed and "Open" (low signal) when pressed.
