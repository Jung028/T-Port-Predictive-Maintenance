# **T-Port Predictive Maintenance 🚀**  

## **Overview**  
This project analyzes **T-Port alignment and crane positioning** to identify **misalignment issues** and ensure accurate **pallet placement** in an **Automated Guided Vehicle (AGV) & Stacker Crane** system.  

## **Objectives**  
- **Detect misalignment** between the AGV QR code, T-Port, and crane fork positions.  
- **Ensure correct fork placement** at T-Port during both **Up (U) and Down (D) positions**.  
- **Visualize and analyze deviations** using statistical methods and data visualization.  
- **Recommend necessary adjustments** (either crane tuning or T-Port modifications).  

---

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
```

### **2️⃣ Install Dependencies**  
```sh
pip install pandas numpy matplotlib seaborn scikit-learn
```

### **3️⃣ Run Analysis**  
```sh
python analyze_tport.py
```

### **4️⃣ Export Results**  
```sh
python export_results.py
```







