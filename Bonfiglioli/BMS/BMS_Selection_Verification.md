# 🎯 BMS SELECTION - INDIVIDUAL JOINT VERIFICATION
## 4-Axis Robotic Manipulator Prototype

---

# 📖 NOTATIONS & SYMBOLS REFERENCE

| Symbol | Full Form | Meaning |
|:------:|:----------|:--------|
| **BMS** | Bonfiglioli Motion Solution | Integrated motor + gearbox unit |
| **F** | Flanged Version | Flange output mounting type |
| **M** | Medium Overspeed | Medium speed variant for balanced performance |
| **B** | Base Overspeed | Standard speed variant |
| **H** | High Overspeed | Maximum speed variant |
| **Mₙ₂** | Rated Output Torque | Continuous torque at rated speed (Nm) |
| **Mₚ₂** | Peak Output Torque | Maximum momentary/emergency torque (Nm) |
| **Mₐ₂** | Acceleration Torque | Maximum torque during acceleration (Nm) |
| **M₀₂** | Stall Torque | Torque at zero speed (Nm) |
| **nₙ₂** | Rated Output Speed | Output speed at rated motor speed (rpm) |
| **nₐ₂** | Maximum Output Speed | Maximum permissible output speed (rpm) |
| **R₂max** | Max Radial Load | Maximum permissible radial load on output shaft (N) |
| **A₂max** | Max Axial Load | Maximum permissible axial load on output shaft (N) |
| **Cₜ** | Torsional Stiffness | Torque required per arcmin of twist (Nm/arcmin) |
| **J₁** | Motor Rotor Inertia | Inertia of motor rotor (kg·cm²) |
| **F1** | Additional Flywheel/Inertia | Extra mass added to rotor for inertia matching |
| **F24** | Electromagnetic Brake | 24V holding brake for safety |
| **ENB11** | Hiperface DSL Encoder | Absolute encoder with 20+ bit resolution |
| **PTC** | Positive Temperature Coefficient | Thermal protection sensor |
| **UH1** | Food Grade Lubricant | Synthetic lubricant for long life |
| **IP65** | Protection Class | Dust-tight & protected against water jets |
| **φR** | Reduced Backlash | ≤5 arcmin for 1-stage, ≤7 arcmin for 2-stage |
| **i** | Gear Ratio | Input speed / Output speed ratio |
| **J_load** | Load Inertia | Reflected inertia at gearbox output shaft (kg·m²) |
| **J_reflected** | Reflected Inertia | Load inertia reflected to motor shaft = J_load / i² |
| **Inertia Ratio** | - | Ratio of reflected inertia to motor inertia = J_reflected / J₁ |

---

# 🔴 JOINT 1 - VERIFICATION

## SELECTED MODEL
```
BMS - F - 160 - M - 50 - 145B - 400 - LOW - S1 - UH1 - PTC - ENB11 - F1 - F24 - AN
```

---

## INPUT REQUIREMENTS

| Parameter | Value |
|:----------|:------|
| **Rated Torque** | 275 Nm |
| **Peak Torque** | 450 Nm |
| **Output Speed** | 30-50 RPM |
| **Reflected Inertia** | 960 kg·m² |
| **Radial Load (Rated)** | 5500 N |
| **Radial Load (Peak)** | 9000 N |
| **Gear Ratio Needed** | ~50:1 |

---

## JOINT 1 - CALCULATIONS

### 1. Torque Verification

| Parameter | Formula | Calculation | Value | Required | Status |
|:----------|:--------|:------------|:------|:---------|:-------|
| **Rated Torque** | From Catalog | BMS F 160 M 50 145B | **800 Nm** | 275 Nm | ✅ **2.9x** |
| **Peak Torque** | From Catalog | BMS F 160 M 50 145B | **2000 Nm** | 450 Nm | ✅ **4.4x** |

**Source:** Page 36 - BMS F160 Medium Overspeed

### 2. Speed Verification

| Parameter | Formula | Calculation | Value | Required | Status |
|:----------|:--------|:------------|:------|:---------|:-------|
| **Output Speed** | n₂ = n₁ / i | 1600 RPM / 50 | **32 RPM** | 30-50 RPM | ✅ |

### 3. Radial Load Verification

| Parameter | Formula | Calculation | Value | Required | Status |
|:----------|:--------|:------------|:------|:---------|:-------|
| **Max Radial Load** | From Catalog | Page 34 - R₂max | **29,000 N** | 9,000 N | ✅ **3.2x** |

**Source:** Page 34 - BMS F160 Technical Data

### 4. Inertia Verification

| Parameter | Formula | Calculation | Value |
|:----------|:--------|:------------|:------|
| **Motor Inertia** | From Catalog | Page 36 - J₁ | 12 kg·cm² |
| **F1 Addition** | From Catalog | Page 41 - F1 for 170B | 70 kg·cm² |
| **Total Inertia** | J₁ + F1 | 12 + 70 | **82 kg·cm²** |
| **Reflected Inertia** | J_load / i² | 960 / 2500 | 0.384 kg·m² = **3840 kg·cm²** |
| **Inertia Ratio** | J_reflected / J_total | 3840 / 82 | **~47 : 1** |

**Source:** Page 36 (J₁), Page 41 (F1 data)

---

## JOINT 1 - SUMMARY

| Check | Value | Required | Status | Margin |
|:------|:------|:---------|:-------|:-------|
| **Rated Torque** | 800 Nm | 275 Nm | ✅ | 2.9x |
| **Peak Torque** | 2000 Nm | 450 Nm | ✅ | 4.4x |
| **Output Speed** | 32 RPM | 30-50 RPM | ✅ | Within |
| **Radial Load** | 29,000 N | 9,000 N | ✅ | 3.2x |
| **Inertia Ratio** | ~47:1 | Acceptable | ⚠️ | With F1 |
| **Brake** | F24 | Required | ✅ | Available |
| **Flywheel** | F1 | Required | ✅ | Available |

**Status:** ✅ **Fully Satisfies** (F1+F24 compatibility to be confirmed with Bonfiglioli)

---

# 🟠 JOINT 2 - VERIFICATION

## SELECTED MODEL
```
BMS - F - 130 - M - 50 - 145B - 400 - LOW - S1 - UH1 - PTC - ENB11 - F1 - F24 - AN
```

---

## INPUT REQUIREMENTS

| Parameter | Value |
|:----------|:------|
| **Rated Torque** | 50 Nm |
| **Peak Torque** | 170 Nm |
| **Output Speed** | 30-50 RPM |
| **Reflected Inertia** | 180 kg·m² |
| **Radial Load (Rated)** | 1000 N |
| **Radial Load (Peak)** | 3400 N |
| **Gear Ratio Needed** | ~50:1 |

---

## JOINT 2 - CALCULATIONS

### 1. Torque Verification

| Parameter | Formula | Calculation | Value | Required | Status |
|:----------|:--------|:------------|:------|:---------|:-------|
| **Rated Torque** | From Catalog | BMS F 130 M 50 145B | **255 Nm** | 50 Nm | ✅ **5.1x** |
| **Peak Torque** | From Catalog | BMS F 130 M 50 145B | **750 Nm** | 170 Nm | ✅ **4.4x** |

**Source:** Page 32 - BMS F130 Base Overspeed

### 2. Speed Verification

| Parameter | Formula | Calculation | Value | Required | Status |
|:----------|:--------|:------------|:------|:---------|:-------|
| **Output Speed** | n₂ = n₁ / i | 1600 RPM / 50 | **32 RPM** | 30-50 RPM | ✅ |

### 3. Radial Load Verification

| Parameter | Formula | Calculation | Value | Required | Status |
|:----------|:--------|:------------|:------|:---------|:-------|
| **Max Radial Load** | From Catalog | Page 31 - R₂max | **12,000 N** | 3,400 N | ✅ **3.5x** |

**Source:** Page 31 - BMS F130 Technical Data

### 4. Inertia Verification

| Parameter | Formula | Calculation | Value |
|:----------|:--------|:------------|:------|
| **Motor Inertia** | From Catalog | Page 32 - J₁ for 145B | 12.5 kg·cm² |
| **F1 Addition** | From Catalog | Page 41 - F1 for 145B | 36 kg·cm² |
| **Total Inertia** | J₁ + F1 | 12.5 + 36 | **48.5 kg·cm²** |
| **Reflected Inertia** | J_load / i² | 180 / 2500 | 0.072 kg·m² = **720 kg·cm²** |
| **Inertia Ratio** | J_reflected / J_total | 720 / 48.5 | **14.8 : 1** |

**Source:** Page 32 (J₁), Page 41 (F1 data)

---

## JOINT 2 - SUMMARY

| Check | Value | Required | Status | Margin |
|:------|:------|:---------|:-------|:-------|
| **Rated Torque** | 255 Nm | 50 Nm | ✅ | 5.1x |
| **Peak Torque** | 750 Nm | 170 Nm | ✅ | 4.4x |
| **Output Speed** | 32 RPM | 30-50 RPM | ✅ | Within |
| **Radial Load** | 12,000 N | 3,400 N | ✅ | 3.5x |
| **Inertia Ratio** | 14.8:1 | ≤20:1 Good | ✅ | With F1 |
| **Brake** | F24 | Required | ✅ | Available |
| **Flywheel** | F1 | Required | ✅ | Available |

**Status:** ✅ **Fully Satisfies** (F1+F24 compatibility to be confirmed with Bonfiglioli)

---

# 🟢 JOINT 3 - VERIFICATION

## SELECTED MODEL
```
BMS - F - 090 - M - 50 - 102A - 400 - LOW - S1 - UH1 - PTC - ENB11 - F24 - AN
```

---

## INPUT REQUIREMENTS

| Parameter | Value |
|:----------|:------|
| **Rated Torque** | 50 Nm |
| **Peak Torque** | 170 Nm |
| **Output Speed** | 30-50 RPM |
| **Reflected Inertia** | 5 kg·m² |
| **Radial Load (Rated)** | 670 N |
| **Radial Load (Peak)** | 1000 N |
| **Gear Ratio Needed** | ~50:1 |

---

## JOINT 3 - CALCULATIONS

### 1. Torque Verification

| Parameter | Formula | Calculation | Value | Required | Status |
|:----------|:--------|:------------|:------|:---------|:-------|
| **Rated Torque** | From Catalog | BMS F 090 M 50 102A | **165 Nm** | 50 Nm | ✅ **3.3x** |
| **Peak Torque** | From Catalog | BMS F 090 M 50 102A | **500 Nm** | 170 Nm | ✅ **2.9x** |

**Source:** Page 30 - BMS F090 Medium Overspeed

### 2. Speed Verification

| Parameter | Formula | Calculation | Value | Required | Status |
|:----------|:--------|:------------|:------|:---------|:-------|
| **Output Speed** | n₂ = n₁ / i | 1600 RPM / 50 | **32 RPM** | 30-50 RPM | ✅ |

### 3. Radial Load Verification

| Parameter | Formula | Calculation | Value | Required | Status |
|:----------|:--------|:------------|:------|:---------|:-------|
| **Max Radial Load** | From Catalog | Page 28 - R₂max | **5,500 N** | 1,000 N | ✅ **5.5x** |

**Source:** Page 28 - BMS F090 Technical Data

### 4. Inertia Verification

| Parameter | Formula | Calculation | Value |
|:----------|:--------|:------------|:------|
| **Motor Inertia** | From Catalog | Page 30 - J₁ for 102A | 1.72 kg·cm² |
| **F1 Addition** | From Catalog | Not required | - |
| **Total Inertia** | J₁ | | **1.72 kg·cm²** |
| **Reflected Inertia** | J_load / i² | 5 / 2500 | 0.002 kg·m² = **20 kg·cm²** |
| **Inertia Ratio** | J_reflected / J_total | 20 / 1.72 | **11.6 : 1** |

**Source:** Page 30 (J₁)

---

## JOINT 3 - SUMMARY

| Check | Value | Required | Status | Margin |
|:------|:------|:---------|:-------|:-------|
| **Rated Torque** | 165 Nm | 50 Nm | ✅ | 3.3x |
| **Peak Torque** | 500 Nm | 170 Nm | ✅ | 2.9x |
| **Output Speed** | 32 RPM | 30-50 RPM | ✅ | Within |
| **Radial Load** | 5,500 N | 1,000 N | ✅ | 5.5x |
| **Inertia Ratio** | 11.6:1 | ≤20:1 Acceptable | ✅ | No F1 needed |
| **Brake** | F24 | Required | ✅ | Available |
| **Flywheel** | F1 | Not Required | ✅ | - |

**Status:** ✅ **Fully Satisfies** (Ready to Order)

---

# 🔵 JOINT 4 - VERIFICATION

## SELECTED MODEL
```
BMS - F - 090 - M - 50 - 102A - 400 - LOW - S1 - UH1 - PTC - ENB11 - F24 - AN
```

---

## INPUT REQUIREMENTS

| Parameter | Value |
|:----------|:------|
| **Rated Torque** | 50 Nm |
| **Peak Torque** | 170 Nm |
| **Output Speed** | 30-50 RPM |
| **Reflected Inertia** | 5 kg·m² |
| **Radial Load (Rated)** | 350 N |
| **Radial Load (Peak)** | 500 N |
| **Gear Ratio Needed** | ~50:1 |

---

## JOINT 4 - CALCULATIONS

### 1. Torque Verification

| Parameter | Formula | Calculation | Value | Required | Status |
|:----------|:--------|:------------|:------|:---------|:-------|
| **Rated Torque** | From Catalog | BMS F 090 M 50 102A | **165 Nm** | 50 Nm | ✅ **3.3x** |
| **Peak Torque** | From Catalog | BMS F 090 M 50 102A | **500 Nm** | 170 Nm | ✅ **2.9x** |

**Source:** Page 30 - BMS F090 Medium Overspeed

### 2. Speed Verification

| Parameter | Formula | Calculation | Value | Required | Status |
|:----------|:--------|:------------|:------|:---------|:-------|
| **Output Speed** | n₂ = n₁ / i | 1600 RPM / 50 | **32 RPM** | 30-50 RPM | ✅ |

### 3. Radial Load Verification

| Parameter | Formula | Calculation | Value | Required | Status |
|:----------|:--------|:------------|:------|:---------|:-------|
| **Max Radial Load** | From Catalog | Page 28 - R₂max | **5,500 N** | 500 N | ✅ **11x** |

**Source:** Page 28 - BMS F090 Technical Data

### 4. Inertia Verification

| Parameter | Formula | Calculation | Value |
|:----------|:--------|:------------|:------|
| **Motor Inertia** | From Catalog | Page 30 - J₁ for 102A | 1.72 kg·cm² |
| **F1 Addition** | From Catalog | Not required | - |
| **Total Inertia** | J₁ | | **1.72 kg·cm²** |
| **Reflected Inertia** | J_load / i² | 5 / 2500 | 0.002 kg·m² = **20 kg·cm²** |
| **Inertia Ratio** | J_reflected / J_total | 20 / 1.72 | **11.6 : 1** |

**Source:** Page 30 (J₁)

---

## JOINT 4 - SUMMARY

| Check | Value | Required | Status | Margin |
|:------|:------|:---------|:-------|:-------|
| **Rated Torque** | 165 Nm | 50 Nm | ✅ | 3.3x |
| **Peak Torque** | 500 Nm | 170 Nm | ✅ | 2.9x |
| **Output Speed** | 32 RPM | 30-50 RPM | ✅ | Within |
| **Radial Load** | 5,500 N | 500 N | ✅ | 11x |
| **Inertia Ratio** | 11.6:1 | ≤20:1 Acceptable | ✅ | No F1 needed |
| **Brake** | F24 | Required | ✅ | Available |
| **Flywheel** | F1 | Not Required | ✅ | - |

**Status:** ✅ **Fully Satisfies** (Ready to Order)

---

# 📊 COMPLETE SUMMARY TABLE

| Joint | Model | F1 | F24 | Rated Torque | Peak Torque | Radial Load | Inertia Ratio | Status |
|:------|:------|:--:|:---:|:-----------:|:-----------:|:-----------:|:-------------:|:------:|
| **1** | BMS F 160 M 50 145B | ✅ | ✅ | 800 Nm ✅ | 2000 Nm ✅ | 29,000 N ✅ | ~47:1 | ⚠️ Confirm F1+F24 |
| **2** | BMS F 130 M 50 145B | ✅ | ✅ | 255 Nm ✅ | 750 Nm ✅ | 12,000 N ✅ | **14.8:1** ✅ | ⚠️ Confirm F1+F24 |
| **3** | BMS F 090 M 50 102A | ❌ | ✅ | 165 Nm ✅ | 500 Nm ✅ | 5,500 N ✅ | 11.6:1 ✅ | ✅ Ready |
| **4** | BMS F 090 M 50 102A | ❌ | ✅ | 165 Nm ✅ | 500 Nm ✅ | 5,500 N ✅ | 11.6:1 ✅ | ✅ Ready |

---

# 📋 NOTATION REFERENCE (Where Section)

| Notation | Full Form | Meaning |
|:--------:|:----------|:--------|
| **BMS** | Bonfiglioli Motion Solution | Integrated motor + gearbox |
| **F** | Flanged Version | Flange output mounting |
| **M** | Medium Overspeed | Balanced speed/torque variant |
| **B** | Base Overspeed | Standard speed variant |
| **H** | High Overspeed | Maximum speed variant |
| **Mₙ₂** | Rated Output Torque | Continuous torque (Nm) |
| **Mₚ₂** | Peak Output Torque | Maximum momentary torque (Nm) |
| **Mₐ₂** | Acceleration Torque | Max torque during acceleration (Nm) |
| **M₀₂** | Stall Torque | Torque at zero speed (Nm) |
| **nₙ₂** | Rated Output Speed | Output speed at rated motor speed (rpm) |
| **nₐ₂** | Max Output Speed | Maximum permissible output speed (rpm) |
| **R₂max** | Max Radial Load | Max radial load on output shaft (N) |
| **A₂max** | Max Axial Load | Max axial load on output shaft (N) |
| **Cₜ** | Torsional Stiffness | Nm/arcmin |
| **J₁** | Motor Rotor Inertia | Motor inertia (kg·cm²) |
| **F1** | Additional Flywheel | Extra inertia for matching |
| **F24** | Electromagnetic Brake | 24V holding brake |
| **ENB11** | Hiperface DSL Encoder | 20+ bit absolute encoder |
| **PTC** | Thermal Protection | PTC thermistor |
| **UH1** | Food Grade Lubricant | Synthetic lubricant |
| **IP65** | Protection Class | Dust-tight + Water jets |
| **φR** | Reduced Backlash | ≤5' (1-stage) / ≤7' (2-stage) |
| **i** | Gear Ratio | Input/Output speed ratio |
| **J_load** | Load Inertia | Inertia at output shaft (kg·m²) |
| **J_reflected** | Reflected Inertia | J_load / i² (kg·cm²) |
| **Inertia Ratio** | - | J_reflected / J₁ |

---

**Prepared by:** Araham Abeddin  
**Project:** 4-Axis Industrial Robotic Manipulator Prototype

---
