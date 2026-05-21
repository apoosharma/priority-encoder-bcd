# priority-encoder-bcd
9-button priority encoder using CD74HC147E IC — press any key and 4 LEDs display its BCD equivalent. Built on breadboard with pull-up resistors and active-LOW logic.
# 🔢 Priority Encoder — Decimal to BCD (74HC147)

A hardware electronics project that encodes a pressed button (1–9) into its 4-bit BCD (Binary Coded Decimal) equivalent using the **CD74HC147E** priority encoder IC. Built on a breadboard with physical push buttons and LEDs.

---

## 📌 What It Does

Press any button (1–9) → 4 LEDs display the BCD equivalent in binary.

| Button Pressed | D | C | B | A | BCD Value |
|:--------------:|:-:|:-:|:-:|:-:|:---------:|
| 1              | 1 | 1 | 1 | 0 | 0001      |
| 2              | 1 | 1 | 0 | 1 | 0010      |
| 3              | 1 | 1 | 0 | 0 | 0011      |
| 4              | 1 | 0 | 1 | 1 | 0100      |
| 5              | 1 | 0 | 1 | 0 | 0101      |
| 6              | 1 | 0 | 0 | 1 | 0110      |
| 7              | 1 | 0 | 0 | 0 | 0111      |
| 8              | 0 | 1 | 1 | 1 | 1000      |
| 9              | 0 | 1 | 1 | 0 | 1001      |

> ⚠️ Outputs are **active LOW** (inverted). LED ON = logic 0.  
> If multiple buttons are pressed, the **highest number takes priority**.

---

## 🧰 Components Used

| Component | Quantity | Purpose |
|-----------|----------|---------|
| CD74HC147E | 1 | Priority encoder IC (decimal to BCD) |
| Push button switches | 9 | Inputs for digits 1–9 |
| LEDs | 4 | Display BCD output bits A, B, C, D |
| 10kΩ resistors | 9 | Pull-up resistors for each input |
| 1kΩ resistors | 4 | Current limiting for LEDs |
| Breadboard | 1 | Circuit assembly |
| Jumper wires | — | Connections |
| 5V power supply | 1 | VCC source |

---

## 📐 Pin Configuration (CD74HC147E)

### Inputs
| Button | IC Pin |
|--------|--------|
| BTN 1  | Pin 1  |
| BTN 2  | Pin 2  |
| BTN 3  | Pin 3  |
| BTN 4  | Pin 4  |
| BTN 5  | Pin 10 |
| BTN 6  | Pin 11 |
| BTN 7  | Pin 12 |
| BTN 8  | Pin 13 |
| BTN 9  | Pin 9* |

> *Verify I9 pin from your specific manufacturer's datasheet.

### Outputs
| Output | IC Pin | LED |
|--------|--------|-----|
| A      | Pin 9  | LED A |
| B      | Pin 7  | LED B |
| C      | Pin 6  | LED C |
| D      | Pin 14 | LED D (MSB) |

### Power
- VCC → Pin 16  
- GND → Pin 8

---

## 🔌 Wiring Summary

For **each button input**:
```
VCC
 |
[10kΩ]
 |——————— IC Input Pin
[BTN]
 |
GND
```

For **each LED output**:
```
IC Output Pin ——— [1kΩ] ——— LED(+) ——— LED(-) ——— GND
```

---

## 🌍 Real-World Applications

- Keyboard matrix encoders
- Interrupt priority controllers in microprocessor systems
- Industrial keypad input systems
- Digital input encoding in embedded systems

---

## 📷 Circuit Photos

> Add your breadboard photos here after building.

---

## ⚙️ How to Test

1. Power the circuit with 5V.
2. Press **Button 5** → LEDs should show `0101` (active LOW: D=1, C=0, B=1, A=0).
3. Press **Button 9** → LEDs should show `1001`.
4. Press **buttons 3 and 7 together** → only 7 registers (priority check).

---

## 📚 Reference

- [CD74HC147E Datasheet — Texas Instruments](https://www.ti.com/product/CD74HC147)

---

## 🏷️ Tags

`electronics` `digital-logic` `breadboard` `priority-encoder` `bcd` `74hc147` `hardware` `beginner-project`
