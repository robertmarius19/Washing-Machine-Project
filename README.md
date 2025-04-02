## 📜 Project Description
This project implements a **washing machine control system** using **VHDL**. The system operates in both **manual** and **automatic** modes, allowing users to select washing parameters such as temperature, speed, pre-wash, and extra rinse. 

The control logic is designed for **FPGA implementation** and consists of various hardware components, including **ROM, counters, multiplexers, and SSD controllers**.

## ✨ Features

### 🔹 **Manual Mode**
- User can set custom washing parameters:
  - **Temperature**: 30°C, 40°C, 60°C, or 90°C.
  - **Speed**: 800, 1000, or 1200 RPM.
  - **Additional Settings**: Pre-wash and extra rinse.

### 🔹 **Automatic Mode**
- Predefined **wash cycles**:
  - **Quick Wash** → 30°C, 1200 RPM, no pre-wash, no extra rinse.
  - **Shirts** → 60°C, 800 RPM, no pre-wash, no extra rinse.
  - **Dark Colors** → 40°C, 1000 RPM, no pre-wash, extra rinse.
  - **Dirty Clothes** → 40°C, 1000 RPM, pre-wash, no extra rinse.
  - **Anti-Allergy** → 90°C, 1200 RPM, no pre-wash, extra rinse.

---

## 🛠 System Architecture
### **Inputs**
- **Mode Selection** (Auto/Manual)
- **Temperature Selection**
- **Speed Selection**
- **Pre-wash Option**
- **Extra Rinse Option**
- **Start, Confirm, Door, Reset Buttons**

### **Control & Execution Unit (VHDL)**
- **ROM** – Stores wash cycle data.
- **Full Adder** – Calculates manual mode times.
- **Multiplexer** – Selects between auto/manual mode.
- **Counters** – Tracks wash cycle time.
- **SSD Controller** – Displays remaining time/status.
- **Frequency Dividers** – Synchronization.
- **OR Gate** – Resets the minute counter.

---

## 🔄 Workflow

1. **Start the machine** → `Start = 1`
2. **Door closed?** → `Door = 1`
3. **Select mode** (Auto/Manual)
4. **Manual Mode**:
   - Select Temperature, Speed, Pre-wash, Extra Rinse.
5. **Auto Mode**:
   - Select a predefined wash program.
6. **Confirm Selection** → `Confirm = 1`
7. **Washing process begins**:  
   - **Main Wash** → **Rinse** → **Spin**
8. **Door unlocks after completion**
9. **Machine stops** → `Start = 0`

---
