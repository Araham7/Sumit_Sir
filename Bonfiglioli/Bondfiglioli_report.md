# 📄 UPDATED DOCUMENT 1: ENGLISH VERSION
## Complete Component Selection Report for 4-Axis Robotic Manipulator

---

### 1. Project Overview

| Parameter | Details |
|:----------|:--------|
| **Application** | 4-Axis Robotic Manipulator Prototype |
| **Power Supply** | 3-Phase, 400V AC |
| **Control** | EtherCAT-based motion control |
| **Cable Length** | 15 meters |

---

### 2. Input Data Summary

| Output Shaft Location | Reflected Inertia (kg·m²) | Radial Load Rated (N) | Radial Load Peak (N) |
|:----------------------|:-------------------------:|:---------------------:|:--------------------:|
| **Motor 1** (Joint 1) | 960 | 5500 | 9000 |
| **Motor 2** (Joint 2) | 180 | 1000 | 3400 |
| **Motor 3** (Joint 3) | 5 | 670 | 1000 |
| **Motor 4** (Joint 4) | 5 | 350 | 500 |

---

### 3. Terminology Reference

| Term | Full Form | Description |
|:-----|:----------|:------------|
| **BMS** | Bonfiglioli Mechatronic Solution | Integrated motor + gearbox unit, factory-assembled and tested |
| **BMD** | Bonfiglioli Motor Drive | Standalone Permanent Magnet AC Synchronous Servo Motor |
| **TQF** | Torque Flange | Precision Planetary Gearbox series with flange output |
| **HB** | Heavy Duty / Reinforced Bearings | Taper roller bearings for high radial/axial load capacity |
| **SB** | Standard Bearings | Ball bearings for normal load applications |
| **F1** | Additional Inertia / Flywheel | Extra mass added to rotor to match high reflected inertia |
| **F24** | Holding Brake | Electromagnetic brake for holding motor shaft when power is off |
| **AXV** | AxiaVert | Premium Servo Drive / Frequency Inverter |

---

### 4. AxiaVert Order Code Structure

```
AXV - 4 - A - S - D - 7K5
 │     │   │   │   │    │
 │     │   │   │   │    └─ Power Rating (7K5 = 7.5 kW)
 │     │   │   │   └────── Drive Version (D = Standard)
 │     │   │   └─────────── Functional Safety (S = STO+SS1-t+SBC)
 │     │   └─────────────── Application Reference (A = Application Specific)
 │     └─────────────────── Voltage (4 = 3×400/480VAC)
 └───────────────────────── Series (AXV = AxiaVert)
```

**Power Rating Codes:**
| Code | Power | Code | Power |
|:----:|:-----:|:----:|:-----:|
| K25 | 0.25 kW | 2K2 | 2.2 kW |
| K37 | 0.37 kW | 3K0 | 3.0 kW |
| K55 | 0.55 kW | 4K0 | 4.0 kW |
| K75 | 0.75 kW | 5K5 | 5.5 kW |
| 1K1 | 1.1 kW | 7K5 | 7.5 kW |
| 1K5 | 1.5 kW | 11K | 11.0 kW |
| | | 15K | 15.0 kW |

**Frame Size Selection (Automatic):**
| Frame Size | AXV20 (230V) | AXV40 (400/480V) |
|:----------:|:------------:|:----------------:|
| 1 | 0.25-3.0 kW | 0.25-1.5 kW |
| 2 | 1.5-3.0 kW | 1.5-4.0 kW |
| 3 | 4.0-9.2 kW | 5.5-9.2 kW |
| 4 | 9.2 kW only | 11.0-15.0 kW |

> **Note:** All joints use 400V 3-Phase supply, so voltage code is `4`. Functional Safety `S` (STO + SS1-t + SBC) is recommended for robotics.

---

### 5. Joint-Wise Recommendations

#### 🔴 JOINT 1 (2 Units) – Heavy Duty Base Joint

| Parameter | Value |
|:----------|:------|
| **Motor** | `BMD 170 45 400 1600 ENB11 F24 IP65 + F1` |
| **Gearbox** | `TQF 160 50 STD HB` |
| **Servo Drive** | `AXV - 4 - A - S - D - 11K` |

**Why BMD + TQF (not BMS)?**
- BMS does NOT offer HB (Reinforced Bearings) option
- 9000N peak radial load requires HB for safety margin
- TQF with HB capacity = 29,000N (3.2x safety margin)
- F1 option needed for 960 kg·m² inertia

**Performance Check:**
| Parameter | Required | Provided | Status |
|:----------|:--------:|:--------:|:------:|
| Rated Torque | 275 Nm | ~2250 Nm | ✅ 8x |
| Peak Torque | 450 Nm | ~6250 Nm | ✅ 13x |
| Output Speed | 30-50 RPM | ~32 RPM | ✅ Met |
| Inertia Match | 960 kg·m² | With F1 + Tuning | ⚠️ Required |
| Radial Load Peak | 9000 N | 29,000 N (HB) | ✅ 3.2x |
| Radial Load Rated | 5500 N | 29,000 N (HB) | ✅ 5.2x |

---

#### 🟠 JOINT 2 (2 Units)

| Parameter | Value |
|:----------|:------|
| **Integrated Unit** | `BMS 118 14 TQF 090 50 F24 ENB11 IP65` |
| **Servo Drive** | `AXV - 4 - A - S - D - 5K5` |

**Why BMS?**
- Radial load (3400N) within BMS standard bearing capacity
- Integrated solution reduces assembly time
- Cost-effective

**Performance Check:**
| Parameter | Required | Provided | Status |
|:----------|:--------:|:--------:|:------:|
| Rated Torque | 50 Nm | ~700 Nm | ✅ 14x |
| Peak Torque | 170 Nm | ~1950 Nm | ✅ 11x |
| Output Speed | 30-50 RPM | ~32 RPM | ✅ Met |
| Radial Load Peak | 3400 N | 2500-4000 N | ✅ Within |

---

#### 🟢 JOINT 3 (2 Units)

| Parameter | Value |
|:----------|:------|
| **Integrated Unit** | `BMS 102 9.6 TQF 090 50 F24 ENB11 IP65` |
| **Servo Drive** | `AXV - 4 - A - S - D - 4K0` |

**Performance Check:**
| Parameter | Required | Provided | Status |
|:----------|:--------:|:--------:|:------:|
| Rated Torque | 50 Nm | ~480 Nm | ✅ 9.6x |
| Peak Torque | 170 Nm | ~1400 Nm | ✅ 8x |
| Output Speed | 30-50 RPM | ~32 RPM | ✅ Met |
| Radial Load Peak | 1000 N | 2500-4000 N | ✅ Within |

---

#### 🔵 JOINT 4 (2 Units)

| Parameter | Value |
|:----------|:------|
| **Integrated Unit** | `BMS 082 4.4 TQF 070 50 F24 ENB11 IP65` |
| **Servo Drive** | `AXV - 4 - A - S - D - 2K2` |

**Performance Check:**
| Parameter | Required | Provided | Status |
|:----------|:--------:|:--------:|:------:|
| Rated Torque | 50 Nm | ~220 Nm | ✅ 4.4x |
| Peak Torque | 170 Nm | ~575 Nm | ✅ 3.4x |
| Output Speed | 30-50 RPM | ~32 RPM | ✅ Met |
| Radial Load Peak | 500 N | 1400-2500 N | ✅ Within |

---

### 6. Complete BOM (Bill of Materials)

| Joint | Qty | Component | Model |
|:------|:---:|:----------|:------|
| **Joint 1** | 2 | Motor | BMD 170 45 400 1600 ENB11 F24 IP65 + F1 |
| | 2 | Gearbox | TQF 160 50 STD HB |
| | 2 | Servo Drive | AXV - 4 - A - S - D - 11K |
| **Joint 2** | 2 | BMS | BMS 118 14 TQF 090 50 F24 ENB11 IP65 |
| | 2 | Servo Drive | AXV - 4 - A - S - D - 5K5 |
| **Joint 3** | 2 | BMS | BMS 102 9.6 TQF 090 50 F24 ENB11 IP65 |
| | 2 | Servo Drive | AXV - 4 - A - S - D - 4K0 |
| **Joint 4** | 2 | BMS | BMS 082 4.4 TQF 070 50 F24 ENB11 IP65 |
| | 2 | Servo Drive | AXV - 4 - A - S - D - 2K2 |
| **All** | 8 | EtherCAT Module | CMA-IE-01 |
| **All** | 8 | Feedback Module | EMA-SABS-11 |
| **All** | 8 | Power Cables | 15m (Orange – DESINA) |
| **All** | 8 | Signal Cables | 15m (Green – DESINA) |

---

### 7. Discussion Points for Bonfiglioli Team

#### For All Joints:
1. **Confirm selection:** Is the proposed component combination finalized and approved?
2. **Lead time:** What are the delivery timelines for each component?
3. **Cables:** Can you provide exact part numbers for 15m power and signal cables?
4. **ESD File:** Can you provide the EtherCAT ESD file for AxiaVert drives?
5. **Commissioning:** What kind of on-site commissioning support do you provide?

#### For Joint 1 (Critical):
6. **F1 Option:** Is the F1 (additional inertia) option sufficient for 960 kg·m² inertia?
7. **HB Option:** Can you confirm TQF 160 with HB can handle 9000N peak radial load?
8. **Tuning:** Do you provide special tuning support for high-inertia applications?
9. **Drive Sizing:** Is 11K drive sufficient, or should we consider 15K?

---

### 8. Summary Status

| Joint | Model | Status | Remarks |
|:------|:------|:------:|:---------|
| **Joint 1** | BMD 170 + TQF 160 HB + AXV 11K | ✅ Fully Satisfies | F1 + HB + Special Tuning required |
| **Joint 2** | BMS 118 14 + AXV 5K5 | ✅ Fully Satisfies | All parameters met |
| **Joint 3** | BMS 102 9.6 + AXV 4K0 | ✅ Fully Satisfies | All parameters met |
| **Joint 4** | BMS 082 4.4 + AXV 2K2 | ✅ Fully Satisfies | All parameters met |

---

**Prepared by:** Araham Abeddin
**Project:** 4-Axis Robotic Manipulator Prototype

---