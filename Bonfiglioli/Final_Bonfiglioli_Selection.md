<!--  (HB = Heavy_Duty/Reinforced Bearings) , (F1 = additional_flywheel/inertia)  -->

# 🎯 BONFIGLIOLI COMPONENT SELECTION RECOMMENDATION

---

# 📖 TERMINOLOGY – BASIC DEFINITIONS

Pehle in terms ko samajh lete hain jo aage use honge:

| Term | Full Form | Kya Hai? | Kahan Use Hota Hai? |
|:-----|:----------|:---------|:--------------------|
| **BMS** | Bonfiglioli Mechatronic Solution | **Integrated Unit** – Motor + Gearbox factory-assembled, pre-tested, ready-to-use | Jab aapko ready-made, plug & play solution chahiye, assembly time bachana ho |
| **BMD** | Bonfiglioli Motor Drive | **Servo Motor** – Permanent Magnet AC Synchronous Motor (Standalone) | Jab aapko alag se motor choose karna ho, custom combination chahiye |
| **TQF** | Torque Flange | **Gearbox Series** – Precision Planetary Gearbox with Flange Output | High torque, high precision, high radial load applications ke liye |
| **HB** | Heavy Duty / Reinforced Bearings | **Taper Roller Bearings** – Output shaft ki radial/axial load capacity badhata hai | High radial load (9000N+) applications ke liye |
| **SB** | Standard Bearings | **Ball Bearings** – Standard radial/axial load capacity | Normal load applications ke liye |
| **F1** | Additional Inertia / Flywheel | **Extra Mass** – Rotor mein additional mass/flywheel add karna | High reflected inertia (960 kg·m²) ko match karne ke liye |
| **F24** | Holding Brake | **Electromagnetic Brake** – Motor shaft ko hold karta hai | Safety ke liye, power off hone par load hold karna |
| **AXV** | AxiaVert | **Servo Drive** – Premium Frequency Inverter/Servo Drive | Motor ko control karne ke liye |

---

# 📖 AxiaVert Order Code Structure

AxiaVert drive ka order code **6 parts** mein banta hai:

```
AXV - 4 - A - S - D - 7K5
 │     │   │   │   │    │
 │     │   │   │   │    └─ Power Rating
 │     │   │   │   └────── Drive Version
 │     │   │   └─────────── Functional Safety
 │     │   └─────────────── Application Reference
 │     └─────────────────── Voltage
 └───────────────────────── Series
```

| Position | Parameter | Code | Meaning |
|:--------:|:----------|:----:|:--------|
| **1** | Series | `AXV` | AxiaVert Series (Fixed) |
| **2** | Voltage | `4` | 3 × 400/480 VAC (3-Phase) |
| **3** | Application Reference | `A` | Application Specific (for robotics) |
| **4** | Functional Safety | `S` | Standard Safety (STO + SS1-t + SBC) |
| **5** | Drive Version | `D` | Standard Drive |
| **6** | Power Rating | `7K5` | 7.5 kW (example) |

> **Note:** For all joints, we are using **400V 3-Phase** supply, so voltage code will always be `4`. Functional Safety `S` (STO + SS1-t + SBC) is recommended for robotics applications.

---

# 📋 INPUT DATA – Customer Requirements

| Output Shaft Location | Maximum Possible Reflected Inertia (kg·m²) | Radial Load Rated (N) | Radial Load Peak (N) |
|:----------------------|:-------------------------:|:---------------------:|:--------------------:|
| **Motor 1** (Joint 1) | 960 | 5500 | 9000 |
| **Motor 2** (Joint 2) | 180 | 1000 | 3400 |
| **Motor 3** (Joint 3) | 5 | 670 | 1000 |
| **Motor 4** (Joint 4) | 5 | 350 | 500 |

---

# 🔥 JOINT 1 ANALYSIS – BMS KYUN NAHI, BMD + TQF WITH HB KYUN?

## ❌ BMS Series (Integrated) – Recommended Nahi Hai

```
┌─────────────────────────────────────────────────────────────────────────────┐
│                                                                             │
│  ❌ WHY BMS IS NOT RECOMMENDED FOR JOINT 1                                │
│                                                                             │
│  1️⃣  NO HB OPTION                                                          │
│     ─────────────────                                                      │
│     BMS is a FIXED integrated unit. Ismein HB (Reinforced Bearings)       │
│     ka option AVAILABLE NAHI HAI.                                         │
│                                                                             │
│  2️⃣  9000N PEAK RADIAL LOAD                                                │
│     ──────────────────────                                                 │
│     BMS standard bearings ki capacity 9000N load ko handle kar sakti       │
│     hai, lekin woh apni PEAK CAPACITY par chalegi.                        │
│                                                                             │
│  3️⃣  BEARING LIFE (L10h) KAM HO JAYEGI                                    │
│     ─────────────────────────────                                          │
│     Peak capacity par chalne se bearing ki life bahut kam ho jayegi.      │
│     System unreliable ho jayega.                                           │
│                                                                             │
│  4️⃣  NO SAFETY MARGIN                                                      │
│     ─────────────────                                                      │
│   9000N load ke liye bearing ki peak capacity = 9000N hai toh koi         │
│   extra margin nahi bachega. Unexpected load aaya toh bearing fail.       │
│                                                                             │
│  5️⃣  WARRANTY VOID HO SAKTI HAI                                            │
│     ─────────────────────────                                              │
│   Agar specified load limit se zyada load par system chalaya toh          │
│   manufacturer ki warranty void ho sakti hai.                             │
│                                                                             │
│  6️⃣  PERFORMANCE RISK                                                      │
│     ─────────────────                                                      │
│   Standard bearing peak capacity par chalegi toh vibration, heat aur      │
│   premature failure ka risk hai.                                          │
│                                                                             │
└─────────────────────────────────────────────────────────────────────────────┘
```

---

## ✅ BMD + TQF with HB (Separate) – Recommended Solution

```
┌─────────────────────────────────────────────────────────────────────────────┐
│                                                                             │
│  ✅ WHY BMD + TQF WITH HB IS RECOMMENDED                                  │
│                                                                             │
│  1️⃣  HB OPTION AVAILABLE                                                   │
│     ────────────────────                                                   │
│     TQF gearbox mein HB (Reinforced Bearings) ek AVAILABLE OPTION hai.    │
│     Aap HB select kar sakte ho.                                            │
│                                                                             │
│  2️⃣  9000N LOAD = WELL WITHIN CAPACITY                                    │
│     ─────────────────────────────                                         │
│     TQF with HB ki RADIAL LOAD CAPACITY 29,000N TAK jaati hai.           │
│     9000N load WELL WITHIN capacity mein hai.                             │
│                                                                             │
│  3️⃣  HIGH SAFETY MARGIN                                                    │
│     ────────────────────                                                   │
│     Capacity = 29,000N, Load = 9,000N                                      │
│     Safety Margin = 20,000N                                                │
│     System bahut safe aur reliable hai.                                   │
│                                                                             │
│  4️⃣  BEARING LIFE (L10h) HIGH                                              │
│     ───────────────────────                                               │
│     Bearing apni capacity ke 31% par chalegi (9000/29000).                 │
│     Bearing life bahut long rahegi.                                       │
│                                                                             │
│  5️⃣  CUSTOMIZABLE                                                          │
│     ────────────                                                           │
│     Aapko exact requirement ke hisaab se motor aur gearbox select karne   │
│     ki freedom hai.                                                        │
│                                                                             │
│  6️⃣  NO PERFORMANCE RISK                                                    │
│     ────────────────────                                                   │
│     System well within capacity chalega. Vibration, heat, aur              │
│     premature failure ka risk nahi hai.                                   │
│                                                                             │
└─────────────────────────────────────────────────────────────────────────────┘
```

---

## 📊 Decision Matrix – BMS vs BMD + TQF with HB (Joint 1)

| Parameter | BMS Series (Integrated) | BMD + TQF with HB (Separate) | Winner |
|:----------|:------------------------:|:----------------------------:|:------:|
| **HB Option Available?** | ❌ No | ✅ Yes | **Separate** |
| **9000N Load Handling** | ❌ At Peak Capacity | ✅ Well Within Capacity | **Separate** |
| **Safety Margin** | ❌ Almost Zero | ✅ Very High (20,000N) | **Separate** |
| **Bearing Life** | ❌ Short (At peak load) | ✅ Long (31% utilization) | **Separate** |
| **Customization** | ❌ Limited | ✅ Full Control | **Separate** |
| **Reliability** | ⚠️ Medium | ✅ High | **Separate** |
| **Assembly Time** | ✅ Pre-assembled | ⚠️ Needs Assembly | **BMS** |
| **Overall Suitability** | ❌ **NOT Recommended** | ✅ **HIGHLY Recommended** | **Separate** |

---

## 🔥 Final Verdict – Joint 1

```
┌─────────────────────────────────────────────────────────────────────────────┐
│                                                                             │
│  ⚠️ CRITICAL DECISION:                                                     │
│                                                                             │
│  Joint 1 ke liye BMS series lena RISKY hai because:                        │
│                                                                             │
│  ✅ 9000N peak radial load = BMS standard bearing ki PEAK CAPACITY par    │
│     chalega                                                               │
│  ✅ Koi SAFETY MARGIN nahi bachega                                         │
│  ✅ Bearing life KAM ho jayegi                                             │
│  ✅ System UNRELIABLE ho jayega                                             │
│                                                                             │
│  ✅ RECOMMENDED: BMD + TQF with HB                                        │
│                                                                             │
│  ✅ 9000N load = TQF with HB ki CAPACITY (29,000N) ke ANDAR hai           │
│  ✅ HIGH SAFETY MARGIN (20,000N)                                           │
│  ✅ Long bearing life                                                      │
│  ✅ Reliable system                                                        │
│                                                                             │
│  💡 BOTTOM LINE:                                                          │
│                                                                             │
│  "BMS convenient hai, lekin HIGH RADIAL LOAD (9000N) ke liye              │
│   SAFE NAHI HAI. BMD + TQF with HB SAFE, RELIABLE aur                     │
│   LONG-LASTING solution hai."                                              │
│                                                                             │
└─────────────────────────────────────────────────────────────────────────────┘
```

---

# ✅ FINAL RECOMMENDATIONS – ALL JOINTS

## 🔴 JOINT 1 (2 Units) – BMD 170 45 + TQF 160 50 with HB

**Motor:** `BMD 170 45 400 1600 ENB11 F24 IP65 + F1`  
**Gearbox:** `TQF 160 50 STD HB`  
**Drive:** `AXV - 4 - A - S - D - 11K`

| Parameter | Required | Having | Status |
|:----------|:---------|:-------|:-------:|
| Rated Torque | 275 Nm | ~2250 Nm | ✅ Exceeded |
| Peak Torque | 450 Nm | ~6250 Nm | ✅ Exceeded |
| Output Speed | 30-50 RPM | ~32 RPM | ✅ Met |
| Reflected Inertia | 960 kg·m² | With F1 option | ⚠️ Requires F1 & Tuning |
| Radial Load Rated | 5500 N | 29,000N (with HB) | ✅ Exceeded |
| Radial Load Peak | 9000 N | 29,000N (with HB) | ✅ Exceeded |
| Gear Type | Precision Planetary | TQF Series with HB | ✅ Met |
| Backlash | Minimized | ≤3 arcmin | ✅ Met |
| Brake | Required | F24 (36 Nm) | ✅ Met |
| Encoder | Absolute ≥12 bit | ENB11 (20+ bit) | ✅ Exceeded |
| Drive Compatibility | EtherCAT | AxiaVert + CMA-IE-01 | ✅ Met |

### 📝 Justification for Joint 1

| Requirement | Our Selection | Justification |
|:------------|:--------------|:--------------|
| **Rated Torque: 275 Nm** | BMD 170 45 (45 Nm) × TQF 160 (50:1) = ~2250 Nm | ✅ 8x higher than required, ample safety margin for peak loads |
| **Peak Torque: 450 Nm** | BMD 170 45 Peak (125 Nm) × 50 = ~6250 Nm | ✅ 13x higher than required, handles emergency stops easily |
| **Output Speed: 30-50 RPM** | 1600 RPM / 50 = 32 RPM | ✅ Perfectly within required range |
| **Reflected Inertia: 960 kg·m²** | F1 (Additional Inertia) option + Special Tuning | ✅ F1 improves inertia ratio, tuning ensures stable control |
| **Radial Load Peak: 9000 N** | TQF 160 with HB = 29,000N capacity | ✅ 3.2x higher than required, huge safety margin |
| **Radial Load Rated: 5500 N** | TQF 160 with HB = 29,000N capacity | ✅ 5.2x higher than required |
| **Why Not BMS?** | BMS mein HB option available nahi hai | ❌ BMS standard bearing peak capacity par chalega, risk high hai |

---

## 🟠 JOINT 2 (2 Units) – BMS 118 14 TQF 090 50

**Integrated Unit:** `BMS 118 14 TQF 090 50 F24 ENB11 IP65`  
**Drive:** `AXV - 4 - A - S - D - 5K5`

| Parameter | Required | Having | Status |
|:----------|:---------|:-------|:-------:|
| Rated Torque | 50 Nm | ~700 Nm | ✅ Exceeded |
| Peak Torque | 170 Nm | ~1950 Nm | ✅ Exceeded |
| Output Speed | 30-50 RPM | ~32 RPM | ✅ Met |
| Reflected Inertia | 180 kg·m² | 7.8 × 10⁻⁴ kg·m² | ✅ Manageable |
| Radial Load Rated | 1000 N | 2500-4000 N | ✅ Met |
| Radial Load Peak | 3400 N | 2500-4000 N | ✅ Met |
| Gear Type | Precision Planetary | TQF Series | ✅ Met |
| Backlash | Minimized | ≤3 arcmin | ✅ Met |
| Brake | Required | F24 (18 Nm) | ✅ Met |
| Encoder | Absolute ≥12 bit | ENB11 (20+ bit) | ✅ Exceeded |
| Drive Compatibility | EtherCAT | AxiaVert + CMA-IE-01 | ✅ Met |

### 📝 Justification for Joint 2

| Requirement | Our Selection | Justification |
|:------------|:--------------|:--------------|
| **Rated Torque: 50 Nm** | BMS 118 14 (14 Nm) × 50 = ~700 Nm | ✅ 14x higher than required |
| **Peak Torque: 170 Nm** | BMS 118 14 Peak (39 Nm) × 50 = ~1950 Nm | ✅ 11x higher than required |
| **Output Speed: 30-50 RPM** | 1600 RPM / 50 = 32 RPM | ✅ Perfectly within required range |
| **Reflected Inertia: 180 kg·m²** | Motor inertia 7.8 × 10⁻⁴ kg·m² | ✅ Manageable with standard tuning |
| **Radial Load Peak: 3400 N** | TQF 090 capacity = 2500-4000 N | ✅ Within capacity, no HB needed |
| **Radial Load Rated: 1000 N** | TQF 090 capacity = 2500-4000 N | ✅ Well within capacity |
| **Why BMS?** | Load BMS standard bearing capacity ke ANDAR hai | ✅ BMS convenient, pre-assembled, cost-effective |

---

## 🟢 JOINT 3 (2 Units) – BMS 102 9.6 TQF 090 50

**Integrated Unit:** `BMS 102 9.6 TQF 090 50 F24 ENB11 IP65`  
**Drive:** `AXV - 4 - A - S - D - 4K0`

| Parameter | Required | Having | Status |
|:----------|:---------|:-------|:-------:|
| Rated Torque | 50 Nm | ~480 Nm | ✅ Exceeded |
| Peak Torque | 170 Nm | ~1400 Nm | ✅ Exceeded |
| Output Speed | 30-50 RPM | ~32 RPM | ✅ Met |
| Reflected Inertia | 5 kg·m² | 4.7 × 10⁻⁴ kg·m² | ✅ Manageable |
| Radial Load Rated | 670 N | 2500-4000 N | ✅ Met |
| Radial Load Peak | 1000 N | 2500-4000 N | ✅ Met |
| Gear Type | Precision Planetary | TQF Series | ✅ Met |
| Backlash | Minimized | ≤3 arcmin | ✅ Met |
| Brake | Required | F24 (9 Nm) | ✅ Met |
| Encoder | Absolute ≥12 bit | ENB11 (20+ bit) | ✅ Exceeded |
| Drive Compatibility | EtherCAT | AxiaVert + CMA-IE-01 | ✅ Met |

### 📝 Justification for Joint 3

| Requirement | Our Selection | Justification |
|:------------|:--------------|:--------------|
| **Rated Torque: 50 Nm** | BMS 102 9.6 (9.6 Nm) × 50 = ~480 Nm | ✅ 9.6x higher than required |
| **Peak Torque: 170 Nm** | BMS 102 9.6 Peak (28 Nm) × 50 = ~1400 Nm | ✅ 8x higher than required |
| **Output Speed: 30-50 RPM** | 1600 RPM / 50 = 32 RPM | ✅ Perfectly within required range |
| **Reflected Inertia: 5 kg·m²** | Motor inertia 4.7 × 10⁻⁴ kg·m² | ✅ Very low, easily manageable |
| **Radial Load Peak: 1000 N** | TQF 090 capacity = 2500-4000 N | ✅ Well within capacity |
| **Radial Load Rated: 670 N** | TQF 090 capacity = 2500-4000 N | ✅ Well within capacity |
| **Why BMS?** | Loads very low, BMS perfectly sufficient | ✅ Cost-effective, convenient, reliable |

---

## 🔵 JOINT 4 (2 Units) – BMS 082 4.4 TQF 070 50

**Integrated Unit:** `BMS 082 4.4 TQF 070 50 F24 ENB11 IP65`  
**Drive:** `AXV - 4 - A - S - D - 2K2`

| Parameter | Required | Having | Status |
|:----------|:---------|:-------|:-------:|
| Rated Torque | 50 Nm | ~220 Nm | ✅ Exceeded |
| Peak Torque | 170 Nm | ~575 Nm | ✅ Exceeded |
| Output Speed | 30-50 RPM | ~32 RPM | ✅ Met |
| Reflected Inertia | 5 kg·m² | 1.7 × 10⁻⁴ kg·m² | ✅ Manageable |
| Radial Load Rated | 350 N | 1400-2500 N | ✅ Met |
| Radial Load Peak | 500 N | 1400-2500 N | ✅ Met |
| Gear Type | Precision Planetary | TQF Series | ✅ Met |
| Backlash | Minimized | ≤3 arcmin | ✅ Met |
| Brake | Required | F24 (4.5 Nm) | ✅ Met |
| Encoder | Absolute ≥12 bit | ENB11 (20+ bit) | ✅ Exceeded |
| Drive Compatibility | EtherCAT | AxiaVert + CMA-IE-01 | ✅ Met |

### 📝 Justification for Joint 4

| Requirement | Our Selection | Justification |
|:------------|:--------------|:--------------|
| **Rated Torque: 50 Nm** | BMS 082 4.4 (4.4 Nm) × 50 = ~220 Nm | ✅ 4.4x higher than required |
| **Peak Torque: 170 Nm** | BMS 082 4.4 Peak (11.5 Nm) × 50 = ~575 Nm | ✅ 3.4x higher than required |
| **Output Speed: 30-50 RPM** | 1600 RPM / 50 = 32 RPM | ✅ Perfectly within required range |
| **Reflected Inertia: 5 kg·m²** | Motor inertia 1.7 × 10⁻⁴ kg·m² | ✅ Very low, easily manageable |
| **Radial Load Peak: 500 N** | TQF 070 capacity = 1400-2500 N | ✅ Well within capacity |
| **Radial Load Rated: 350 N** | TQF 070 capacity = 1400-2500 N | ✅ Well within capacity |
| **Why BMS?** | Smallest load, smallest BMS sufficient | ✅ Most cost-effective solution |

---

# 📋 COMPLETE BOM (Bill of Materials)

| Joint | Qty | Component | Model |
|:------|:---:|:----------|:------|
| **Joint 1** | 2 | Motor | BMD 170 45 400 1600 ENB11 F24 IP65 + F1 |
| | 2 | Gearbox | TQF 160 50 STD HB |
| | 2 | Servo Drive | **AXV - 4 - A - S - D - 11K** |
| **Joint 2** | 2 | BMS | BMS 118 14 TQF 090 50 F24 ENB11 IP65 |
| | 2 | Servo Drive | **AXV - 4 - A - S - D - 5K5** |
| **Joint 3** | 2 | BMS | BMS 102 9.6 TQF 090 50 F24 ENB11 IP65 |
| | 2 | Servo Drive | **AXV - 4 - A - S - D - 4K0** |
| **Joint 4** | 2 | BMS | BMS 082 4.4 TQF 070 50 F24 ENB11 IP65 |
| | 2 | Servo Drive | **AXV - 4 - A - S - D - 2K2** |
| **All** | 8 | EtherCAT Module | CMA-IE-01 |
| **All** | 8 | Feedback Module | EMA-SABS-11 |
| **All** | 8 | Power Cables | 15m (Orange – DESINA) |
| **All** | 8 | Signal Cables | 15m (Green – DESINA) |

---

# 📊 POWER RATING CODES REFERENCE

| Code | Power | Code | Power |
|:----:|:-----:|:----:|:-----:|
| `K25` | 0.25 kW | `2K2` | 2.2 kW |
| `K37` | 0.37 kW | `3K0` | 3.0 kW |
| `K55` | 0.55 kW | `4K0` | 4.0 kW |
| `K75` | 0.75 kW | `5K5` | 5.5 kW |
| `1K1` | 1.1 kW | `7K5` | 7.5 kW |
| `1K5` | 1.5 kW | `11K` | 11.0 kW |
| | | `15K` | 15.0 kW |

---

# 🔧 ADDITIONAL OPTIONS EXPLANATION

## 1️⃣ F1 (Additional Inertia / Flywheel)

| Aspect | Detail |
|:-------|:--------|
| **Kya Hai?** | Motor ke rotor mein extra mass (flywheel) add karna |
| **Kyun Chahiye?** | 960 kg·m² inertia bahut high hai. F1 se motor ka apna inertia increase hota hai, jisse motor aur load ka inertia ratio better ho jata hai |
| **Effect** | Motor ko heavy load control karne mein easy hota hai, oscillation kam hoti hai, system stable rehta hai |
| **Catalogue Reference** | BMD catalogue page 19 – "additional flywheel / inertia" |
| **Joint 1 Mein** | ✅ Required (kyunki 960 kg·m² inertia) |

---

## 2️⃣ HB (Reinforced Bearings)

| Aspect | Detail |
|:-------|:--------|
| **Kya Hai?** | Heavy Duty / Reinforced bearings, specifically taper roller bearings |
| **Kyun Chahiye?** | Joint 1 par 9000N peak radial load hai, jo standard bearing (SB) ki capacity se bahut zyada hai |
| **Effect** | Gearbox ki radial aur axial load handling capacity badh jati hai |
| **Example** | TQ 070 mein SB capacity 4200N, HB capacity 9000N |
| **Catalogue Reference** | Gearbox catalogue mein "reinforced bearings" option |
| **Joint 1 Mein** | ✅ Required (kyunki 9000N peak radial load) |

---

## 3️⃣ Tuning (Servo Tuning)

| Aspect | Detail |
|:-------|:--------|
| **Kya Hai?** | Software-level adjustment process – servo drive ke PID gains, bandwidth, aur control parameters adjust karna |
| **Kyun Chahiye?** | 960 kg·m² inertia ke saath standard PID settings se motor oscillate, overshoot, ya unstable ho sakta hai |
| **Effect** | Motor smooth, accurate, aur predictable motion deliver karta hai |
| **Process** | Position loop, velocity loop, aur current loop ke gains adjust karna |
| **Joint 1 Mein** | ✅ Required (high inertia ko handle karne ke liye) |

---

# 📊 SUMMARY – OVERALL STATUS

| Joint | Recommended Model | Status | Key Justification |
|:------|:------------------|:------:|:------------------|
| **Joint 1** | BMD 170 45 + TQF 160 50 with HB + AXV 11K | ✅ **Fully Satisfies** | HB handles 9000N load with 3x safety margin; F1 + Tuning handles 960 kg·m² inertia |
| **Joint 2** | BMS 118 14 TQF 090 50 + AXV 5K5 | ✅ **Fully Satisfies** | 3400N load within BMS capacity; convenient integrated solution |
| **Joint 3** | BMS 102 9.6 TQF 090 50 + AXV 4K0 | ✅ **Fully Satisfies** | 1000N load well within BMS capacity; cost-effective |
| **Joint 4** | BMS 082 4.4 TQF 070 50 + AXV 2K2 | ✅ **Fully Satisfies** | 500N load well within BMS capacity; most economical |

---

# ✅ BOTTOM LINE

| Question | Answer |
|:---------|:-------|
| **Joint 1 ke liye BMS kyun nahi?** | BMS mein HB (Reinforced Bearings) option available nahi hai. 9000N load peak capacity par chalega, jisse bearing life kam, reliability kam, aur risk high hai |
| **Joint 1 ke liye BMD + TQF with HB kyun?** | TQF mein HB option available hai. 9000N load well within capacity (29,000N) mein hai. High safety margin, long bearing life, aur reliable system |
| **Joint 2, 3, 4 ke liye BMS kyun?** | Loads (3400N, 1000N, 500N) BMS standard bearing capacity ke andar hain, isliye BMS sufficient, convenient aur cost-effective hai |
| **Overall system satisfy kar raha hai?** | ✅ **YES** – All joints covered with appropriate solutions. Joint 1 gets separate components for high load, Joints 2-4 get integrated BMS for convenience |

---
