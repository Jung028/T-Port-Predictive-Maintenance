# **T-Port Predictive Maintenance 🚀**  

![image](https://github.com/user-attachments/assets/e1f599e1-cff7-463c-ab55-72e3e924b6b7)

## **Overview**  
This project analyzes **T(Transport)-Port alignment and crane positioning** to identify **misalignment issues** and ensure accurate **pallet placement** in an **Automated Guided Vehicle (AGV) & Stacker Crane** system.  

## **Objectives**  
- **Detect misalignment** between the AGV QR code, T-Port, and crane fork positions.  
- **Ensure correct fork placement** at T-Port during both **Up (U) and Down (D) positions**.  
- **Visualize and analyze deviations** using statistical methods and data visualization.  
- **Recommend necessary adjustments** (either crane tuning or T-Port modifications).  

**Explaination**
- **U and D Positions** are measured to ensure the fork and T-Ports height are within the acceptable range of 25-40mm for D, and 95-105mm for U, to ensure that the fork doesnt hit the T-Port or Pallet during extension / retraction.

**Methodology**
- **Measurement of T-port and Fork Data** are measured through manual operation of crane position at T-Port, then extension of fork. Then changed to auto operation for simulating actual movemnet protocol. Operation steps are as below:
1. **TO - Retrive** - Enter values (level-crane-port number), e.g. Crane 34 at level 2, Out Port, Select Retrive, then enter (2342)
2. **TI - Store**  - Enter values (level-crane-port number), e.g. Crane 34 at level 2, In Port, Select Store, then enter (2341)

- **1 (I Port Home), 2 (O Port Home), 3 (O Port Opposite Home), 4 (I Port Opposite Home)**

---

![image](https://github.com/user-attachments/assets/f2d68dde-771f-453f-aac2-d3838027fe57)


## **Data Analysis Steps**  

### **Step 1: Data Collection**  
- Load **TI.csv** and **TO.csv** datasets.  
- Extract relevant fields:  
  - `Crane No.`  
  - `Fork Center To T-Port Center Distance`  
  - `Crane Move Center To T-Port Distance`  
  - `U Position Fork To T-Port Distance`  
  - `D Position Fork To T-Port Distance`  

---

### **Step 2: Data Exploration & Cleaning**  
- Check for **missing values** and **outliers**.  
- Compute **summary statistics**.  
- Prepare data for **visualization and modeling**.  
- **Identify misaligned cranes** based on thresholds:  
  - `|distance| > 5mm` → **Misaligned**  

---

### **Step 3: Correlation Analysis**  
- Determine relationships between:  
  - `Fork Center To T-Port Center Distance`  
  - `Crane Move Center To T-Port Distance`  
- Identify **patterns of misalignment** to suggest corrections.  

---

### **Step 4: T-Port Position Analysis**  
- **Verify U and D positions**:  
  - **D (Down) Position** should be **25–40mm**.  
  - **U (Up) Position** should be **95–105mm**.  
- Identify **T-Ports that are out of range** and require adjustments.  

---

## **Why This Analysis Matters**  

### 🔍 **Crane Move Center to T-Port Distance**  
- Ensures **QR alignment** for correct AGV positioning.  
- Prevents **misplaced pallets**, reducing risk of **breakage or tilting**.  
- Determines whether **stacker crane tuning** or **floor adjustments** are needed.  

### 🔍 **Fork Center to T-Port Center Distance**  
- Ensures the **fork aligns at the center** of the pallet.  
- Prevents **collisions with profile sensors** or **oversize errors**, avoiding manual intervention.  

---

## **Results & Adjustments**  

### ✅ **Actions Taken**  
- **T-Port Adjustments**: 3D-printed material added to align pallets.  
- **Crane Alignment**: Communicated with Muratec to **adjust Crane 28 positioning**.  

### 📊 **Exported Reports**  
- Misaligned cranes & T-Ports exported to `Misaligned_TPorts.csv`.  

---

## **Installation & Usage**  

### **1️⃣ Clone Repository**  
```sh
git clone https://github.com/Jung028/T-Port-Predictive-Maintenance.git
cd T-Port-Predictive-Maintenance
cd Ti_To_Analysis
```

### **2️⃣ Install Dependencies**  
```sh
pip install pandas numpy matplotlib seaborn scikit-learn
pip install jupyterlab
```

### **3️⃣ Run Analysis**  
```sh
jupyter lab TI_TO.ipynb
```

---

## **Next Steps**  

  
1. Create a dashboard to show analysis of all the cranes and T-Port alignment
2. Update the newly collected data for Level 1A and 2A


---

## **Acknowledgments**  

Special thanks to the Logiflow Team at ALPM who contributed to the data collection of the T-Ports and Stacker Cranes! 🚀

---




