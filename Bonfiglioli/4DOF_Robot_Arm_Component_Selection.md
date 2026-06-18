## 📋 COMPONENT SELECTION RECOMMENDATION
### For Robotic Manipulator Application

---

## 1️⃣ MOTOR SELECTION (BMD Series)

### Motor - 1 (Joint 1) - 2 Units

| Parameter | Requirement | Recommended BMD Model |
|:----------|:------------|:---------------------|
| Rated Torque | 275 Nm | BMD 170 - 45 Nm × Gear Ratio |
| Peak Torque | 450 Nm | BMD 170 (Peak: 125 Nm) × Ratio |
| Rated Speed | 30-50 RPM | Need Gear Ratio ~40-60:1 |
| Mounting | Flange | B5 Flange Variant |
| Encoder | Absolute ≥12 bit | ENB11/ENB12 (Hiperface DSL, 20+ bit) |

**Recommended:** `BMD 170 45 400 1600 ENB11 F24 IP65` (2 Units)

| Specification | Value |
|:--------------|:------|
| Stall Torque (M₀) | 45 Nm |
| Max Torque (Mₘₐₓ) | 125 Nm |
| Rated Speed | 1600-6000 rpm |
| Voltage | 400V |
| Feedback | ENB11 - Hiperface DSL Multi-turn (20 bit) |
| Brake | F24 (36 Nm holding brake) |
| Protection | IP65 |
| Inertia (J) | 31 × 10⁻⁴ kg·m² |
| Mass | ~29 kg |

---

### Motor - 2 (Joint 2, 3 & 4) - 6 Units

| Parameter | Requirement | Recommended BMD Model |
|:----------|:------------|:---------------------|
| Rated Torque | 50 Nm | BMD 118 - 14 Nm × Gear Ratio |
| Peak Torque | 170 Nm | BMD 118 (Peak: 39 Nm) × Ratio |
| Rated Speed | 30-50 RPM | Need Gear Ratio ~35-50:1 |
| Mounting | Flange | B5 Flange Variant |
| Encoder | Absolute ≥12 bit | ENB11/ENB12 (Hiperface DSL, 20+ bit) |

**Recommended:** `BMD 118 14 400 1600 ENB11 F24 IP65` (6 Units)

| Specification | Value |
|:--------------|:------|
| Stall Torque (M₀) | 14 Nm |
| Max Torque (Mₘₐₓ) | 39 Nm |
| Rated Speed | 1600-6000 rpm |
| Voltage | 400V |
| Feedback | ENB11 - Hiperface DSL Multi-turn (20 bit) |
| Brake | F24 (18 Nm holding brake) |
| Protection | IP65 |
| Inertia (J) | 9.9 × 10⁻⁴ kg·m² |
| Mass | ~11.7 kg |

---

## 2️⃣ GEARBOX SELECTION (TQF Series)

### Gearbox Selection Criteria

| Parameter | Motor 1 (Joint 1) | Motor 2 (Joint 2-4) |
|:----------|:-----------------:|:-------------------:|
| Required Output Torque | 275 Nm (Rated) | 50 Nm (Rated) |
| Required Output Torque | 450 Nm (Peak) | 170 Nm (Peak) |
| Output Speed | 30-50 RPM | 30-50 RPM |
| Motor Rated Speed | 1600 RPM | 1600 RPM |
| Required Ratio | **~40-50:1** | **~35-50:1** |
| Reflected Inertia | 960 kg·m² | 180 kg·m² (Joint 2) |
| Radial Load (Rated/Peak) | 5500/9000 N | 1000/3400 N |

---

### Gearbox - 1 (Joint 1) - TQF Series

**Recommended:** `TQF 160 - 50 - STD` (Ratio 50:1) - 2 Units

| Specification | Value |
|:--------------|:------|
| Frame Size | 160 |
| Ratio (i) | 50 |
| Rated Output Torque (Mₙ₂) | 2500-3500 Nm ✅ |
| Max Acceleration Torque (Mₐ₂) | 3500 Nm |
| Emergency Stop Torque (Mₚ₂) | 3500 Nm |
| Backlash | STD ≤5' / Reduced ≤3' |
| Torsional Stiffness (Cₜ) | 35 Nm/arcmin |
| Max Radial Load (R₂ max) | 6500-7500 N ✅ |
| Max Axial Load (A₂ max) | 5500-6500 N ✅ |
| Max Tilting Moment | 1200-3700 Nm |
| Efficiency (η) | 97% (1-stage) |
| Protection | IP65 |
| Mass Moment of Inertia (Jg) | ~3.2 - 6.5 kgcm² |

**Why TQF 160?**
- ✅ Handles 9000N peak radial load (R₂ max 6500-7500N with reinforced bearings)
- ✅ Output torque 275/450Nm easily within 2500-3500Nm range
- ✅ Ratio 50:1 gives output speed ~32 RPM at 1600 RPM input
- ✅ IP65 protection for industrial environment

---

### Gearbox - 2 (Joint 2, 3 & 4) - TQF Series

**Recommended:** `TQF 090 - 50 - STD` (Ratio 50:1) - 6 Units

| Specification | Value |
|:--------------|:------|
| Frame Size | 090 |
| Ratio (i) | 50 |
| Rated Output Torque (Mₙ₂) | 500-1250 Nm ✅ |
| Max Acceleration Torque (Mₐ₂) | 500-1250 Nm |
| Emergency Stop Torque (Mₚ₂) | 500-1250 Nm |
| Backlash | STD ≤5' / Reduced ≤3' |
| Torsional Stiffness (Cₜ) | 25-50 Nm/arcmin |
| Max Radial Load (R₂ max) | 2500-4000 N ✅ |
| Max Axial Load (A₂ max) | 2500-4000 N ✅ |
| Efficiency (η) | 97% (1-stage) |
| Protection | IP65 |
| Mass Moment of Inertia (Jg) | ~1.5 - 2.5 kgcm² |

**Why TQF 090?**
- ✅ Handles 3400N peak radial load (R₂ max 2500-4000N)
- ✅ Output torque 50/170Nm within range
- ✅ Ratio 50:1 gives output speed ~32 RPM
- ✅ More compact than TQF 130

---

## 3️⃣ SERVO DRIVE SELECTION (AxiaVert Series)

### Drive Requirements:

| Parameter | Requirement |
|:----------|:------------|
| Protocol | EtherCAT |
| Control Modes | Position, Velocity, Torque |
| Power Supply | Three Phase 400V |
| Cable Length | 15 m |
| Feedback | Absolute Encoder (Hiperface DSL) |
| Functional Safety | Required for robotics |

---

### Recommended Drive: `AXV 4 A S D 7K5` (For Motor 1)

| Specification | Value |
|:--------------|:------|
| Series | AXV40 (3×400/480V) |
| Power Rating | 7.5 kW (9.2 kW available) |
| Rated Current | 32 A |
| Peak Current | 48 A (150% overload) |
| Drive Version | A (IIoT + PLC) or D (Standard) |
| Functional Safety | S (STO + SS1-t + SBC) |
| Application Reference | A (Application Specific) |
| Feedback Module | EMA-SABS-11 (Hiperface DSL) |
| Communication | CMA-IE-01 (EtherCAT) |

---

### Recommended Drive: `AXV 4 A S D 3K0` (For Motor 2)

| Specification | Value |
|:--------------|:------|
| Series | AXV40 (3×400/480V) |
| Power Rating | 3.0 kW |
| Rated Current | 7.8 A |
| Peak Current | 11.7 A (150% overload) |
| Drive Version | A (IIoT + PLC) or D (Standard) |
| Functional Safety | S (STO + SS1-t + SBC) |
| Application Reference | A (Application Specific) |
| Feedback Module | EMA-SABS-11 (Hiperface DSL) |
| Communication | CMA-IE-01 (EtherCAT) |

---

## 4️⃣ COMPLETE BOM (Bill of Materials)

| Component | Model | Quantity | Application |
|:----------|:------|:--------:|:------------|
| **Motor 1** | BMD 170 45 400 1600 ENB11 F24 IP65 | 2 | Joint 1 |
| **Motor 2** | BMD 118 14 400 1600 ENB11 F24 IP65 | 6 | Joint 2, 3, 4 |
| **Gearbox 1** | TQF 160 50 STD | 2 | Joint 1 |
| **Gearbox 2** | TQF 090 50 STD | 6 | Joint 2, 3, 4 |
| **Drive 1** | AXV 4 A S D 7K5 | 2 | Joint 1 |
| **Drive 2** | AXV 4 A S D 3K0 | 6 | Joint 2, 3, 4 |
| **Feedback Module** | EMA-SABS-11 | 8 | All Motors |
| **EtherCAT Module** | CMA-IE-01 | 8 | All Drives |
| **Power Cable** | 15 m (Orange - DESINA) | 8 | All Motors |
| **Signal Cable** | 15 m (Green - DESINA) | 8 | All Motors |
| **Keypad** | KPA-DSP-01 | 8 | Optional |

---

## 5️⃣ INTEGRATED SOLUTION - BMS Option

Instead of separate Motor + Gearbox, you can also consider **BMS Series** - Integrated Servo Gearmotor.

### BMS Selection:

| Application | Recommended BMS Model |
|:------------|:----------------------|
| Joint 1 | BMS - 170 - 45 - TQF - 160 - 50 |
| Joint 2, 3, 4 | BMS - 118 - 14 - TQF - 090 - 50 |

**Benefits of BMS:**
- ✅ Pre-assembled, tested unit
- ✅ Reduced assembly time
- ✅ Optimized for performance
- ✅ Compact design
- ✅ Single part number for ordering

---

## 6️⃣ ADDITIONAL RECOMMENDATIONS

### For Motor 1 (Joint 1) - With 960 kg·m² Reflected Inertia

```
┌─────────────────────────────────────────────────────────────┐
│  ⚠️ HIGH INERTIA ALERT - 960 kg·m²                          │  
│                                                             │ 
│  ✅ Inertia Ratio = J_load / J_motor                        │ 
│  ✅ J_load = 960 kg·m²                                      │  
│  ✅ J_motor (BMD 170) = 31 × 10⁻⁴ kg·m²                     │  
│  ✅ Ratio = 960 / 0.0031 = 309,677 : 1                      │  
│                                                             │
│  ⚠️ This is EXTREMELY HIGH!                                 │
│                                                             │
│  💡 RECOMMENDATIONS:                                        │
│  ✅ Use larger motor (BMD 170 with 60 Nm forced vent)       │
│  ✅ Add additional inertia matching flywheel                │
│  ✅ Use servo tuning with inertia estimation                │
│  ✅ Consider motor with higher torque/inertia ratio         │
│  ✅ May need special control algorithms                     │
│                                                             │
│  💡 Suggest using BMS integrated unit for optimized         │
│     inertia matching                                        │
│                                                             │
└─────────────────────────────────────────────────────────────┘
```

### For Other Joints - With 5 kg·m² Reflected Inertia

- ✅ Much better inertia ratio
- ✅ Standard tuning will work
- ✅ No special considerations

---

## 📊 Summary Table

| Component | Joint 1 (x2) | Joint 2, 3, 4 (x6) |
|:----------|:------------:|:------------------:|
| Motor | BMD 170 45 | BMD 118 14 |
| Gearbox | TQF 160 50 | TQF 090 50 |
| Ratio | 50:1 | 50:1 |
| Drive | AXV 4 A S D 7K5 | AXV 4 A S D 3K0 |
| Feedback | ENB11 (Hiperface DSL) | ENB11 (Hiperface DSL) |
| Brake | 36 Nm holding brake | 18 Nm holding brake |
| Protection | IP65 | IP65 |

---

## 🎯 Final Recommendation

```
┌─────────────────────────────────────────────────────────────┐
│                                                             │
│  ✅ RECOMMENDATION SUMMARY:                                 │
│                                                             │
│  Motor + Gearbox (Separate):                                │
│  BMD 170 45 + TQF 160 50 × 2 (Joint 1)                      │
│  BMD 118 14 + TQF 090 50 × 6 (Joint 2-4)                    │
│  AxiaVert Drive × 8                                         │
│                                                             │
│  OR                                                         │
│                                                             │
│  Integrated Solution (BMS):                                 │
│  BMS 170 45 TQF 160 50 × 2                                  │
│  BMS 118 14 TQF 090 50 × 6                                  │
│  AxiaVert Drive × 8                                         │
│                                                             │
│  🔥 For Joint 1, the 960 kg·m² reflected inertia is         │
│     extremely high. Recommend consulting Bonfiglioli        │
│     engineering team for special tuning.                    │
│                                                             │
└─────────────────────────────────────────────────────────────┘
```
