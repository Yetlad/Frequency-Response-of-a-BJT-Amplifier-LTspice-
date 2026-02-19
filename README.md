
# – BJT Common-Emitter Amplifier (LTspice)

## Circuit Parameters

| Component  | Value  |
| ---------- | ------ |
| Cs         | 10 µF  |
| Cc         | 1 µF   |
| CE         | 20 µF  |
| R1         | 40 kΩ  |
| R2         | 10 kΩ  |
| RC         | 4 kΩ   |
| RE         | 2 kΩ   |
| RL         | 2.2 kΩ |
| VCC        | 20 V   |
| Transistor | 2N2222 |

AC Analysis Command:

```
.ac dec 200 0.1 100Meg
```

Plot:

```
dB(V(vout)/V(vin))
```

---

## 1. Midband Gain

From the AC simulation plot:

* **Midband Gain ≈ 32 dB**

Convert to linear scale:

[
A_v = 10^{(32/20)} ≈ 40
]

**Midband Gain ≈ 40 V/V**

---

## 2. Lower Cutoff Frequency (–3 dB)

* Midband gain = 32 dB
* –3 dB level = 29 dB

From the graph:

**Lower cutoff frequency ≈ 40 Hz**

---

## 3. Capacitor Dominating Low-Frequency Response

The amplifier contains three capacitors affecting low-frequency behavior:

* Input coupling capacitor (Cs)
* Output coupling capacitor (Cc)
* Emitter bypass capacitor (CE)

The dominant capacitor is:

**Emitter bypass capacitor (CE)**

Because at low frequency it does not fully bypass RE, reducing gain significantly.

---

## 4. Why It Is Not a Single-Pole High-Pass

The circuit has **three capacitors**, each introducing a low-frequency pole.

Therefore:

* The roll-off is not a single 20 dB/decade slope.
* The response is a **multi-pole high-pass characteristic**.

---

## Final Results

* Midband Gain: **32 dB (≈ 40 V/V)**
* Lower Cutoff Frequency: **≈ 40 Hz**
* Dominant Capacitor: **Emitter bypass capacitor (CE)**
* Response Type: **Multi-pole high-pass**

---
