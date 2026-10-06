# RF Fundamentals & Link Metrics
## 1. Objective

The objective of this task is to understand the basic RF and link-metric concepts required for later RF/DSP simulation work.

The task covers:

- Frequency
- Time period
- Bandwidth
- Center frequency
- Sampling rate
- Nyquist sampling condition
- Noise
- Signal-to-Noise Ratio (SNR)
- Basic RF link metrics

---

# 2. Frequency

Frequency represents the number of cycles completed by a periodic signal in one second.

It is represented by **f** and its SI unit is **Hertz (Hz)**.

### Common Units

- 1 kHz = 1,000 Hz
- 1 MHz = 1,000,000 Hz
- 1 GHz = 1,000 MHz

### Formula

`f = 1 / T`

Where:

- `f` = frequency
- `T` = time period

---

## Numerical Example 1 — Frequency

A signal completes **5,000 cycles in one second**. Find its frequency.

### Solution

Frequency = cycles per second.

`f = 5000 Hz`

Therefore:

**Answer: 5 kHz**

---

# 3. Time Period

Time period is the time required to complete one complete cycle of a periodic signal.

It is represented by **T**.

### Formula

`T = 1 / f`

### Useful Shortcut

When frequency is given in MHz:

`T (µs) = 1 / f (MHz)`

For example:

`f = 5 MHz`

`T = 1 / 5 = 0.2 µs`

---

## Numerical Example 2 — Time Period

A signal has a frequency of **4 MHz**. Find its time period.

### Solution

`T = 1 / f`

`T = 1 / 4`

`T = 0.25 µs`

**Answer: 0.25 µs**

---

# 4. Bandwidth

Bandwidth represents the width of the frequency range occupied by a signal.

It is calculated using the upper and lower frequency limits.

### Formula

`BW = f_high - f_low`

Where:

- `f_high` = upper frequency
- `f_low` = lower frequency

---

## Numerical Example 3 — Bandwidth

A signal occupies the frequency range from **2.40 GHz to 2.50 GHz**. Find the bandwidth.

### Solution

`BW = f_high - f_low`

`BW = 2.50 - 2.40`

`BW = 0.10 GHz`

Since:

`1 GHz = 1000 MHz`

`0.10 GHz = 100 MHz`

**Answer: 100 MHz**

---

# 5. Center Frequency

Center frequency is the midpoint of the lower and upper frequency limits.

### Formula

`f_c = (f_low + f_high) / 2`

---

## Numerical Example 4 — Center Frequency

A signal has:

- Lower frequency = 2.40 GHz
- Upper frequency = 2.50 GHz

Find the center frequency.

### Solution

`f_c = (2.40 + 2.50) / 2`

`f_c = 4.90 / 2`

`f_c = 2.45 GHz`

**Answer: 2.45 GHz**

---

# 6. Sampling

Sampling is the process of measuring a continuous-time signal at discrete time intervals to obtain a digital representation.

The number of samples taken per second is called the **sampling rate**.

It is represented by `f_s`.

### Unit

Samples per second, commonly expressed in Hz, kHz, or MHz.

---

# 7. Nyquist Sampling Condition

For a signal to be sampled without violating the basic Nyquist condition, the sampling rate should be at least twice the maximum frequency component.

### Formula

`f_s >= 2 × f_max`

Where:

- `f_s` = sampling rate
- `f_max` = maximum signal frequency

---

## Numerical Example 5 — Minimum Sampling Rate

The maximum frequency component of a signal is **15 MHz**. Find the minimum sampling rate.

### Solution

`f_s >= 2 × f_max`

`f_s >= 2 × 15`

`f_s >= 30 MHz`

**Answer: Minimum sampling rate = 30 MHz**

---

## Numerical Example 6 — Checking Sampling Rate

A signal has a maximum frequency of **8 MHz** and the system sampling rate is **20 MHz**. Is the sampling rate sufficient according to the Nyquist condition?

### Solution

Minimum required sampling rate:

`2 × 8 = 16 MHz`

Actual sampling rate:

`20 MHz`

Since:

`20 MHz > 16 MHz`

The sampling rate is sufficient according to the basic Nyquist condition.

**Answer: Yes, it is sufficient.**

---

# 8. Aliasing

If a signal is sampled below the required Nyquist rate, different frequency components can become indistinguishable in the sampled representation. This effect is called **aliasing**.

Therefore, an insufficient sampling rate can produce an incorrect representation of the original signal.

---

## Numerical Example 7 — Identifying Insufficient Sampling

A signal has a maximum frequency of **10 MHz** and is sampled at **15 MHz**. Is the sampling rate sufficient?

### Solution

Minimum required sampling rate:

`2 × 10 = 20 MHz`

Actual sampling rate:

`15 MHz`

Since:

`15 MHz < 20 MHz`

The sampling rate is not sufficient.

**Answer: No. The Nyquist condition is not satisfied, so aliasing can occur.**

---

# 9. Noise

Noise is an unwanted disturbance that can affect a useful signal.

A basic representation is:

`Received Signal = Useful Signal + Noise`

Noise can reduce signal quality and make reliable signal interpretation more difficult.

For this task, noise is treated as an unwanted component when evaluating signal quality using SNR.

---

## Numerical Example 8 — Signal and Noise Power

A received signal contains:

- Useful signal power = 100 W
- Noise power = 5 W

The signal-to-noise ratio can be calculated from these two powers.

`SNR = P_signal / P_noise`

`SNR = 100 / 5`

`SNR = 20`

**Answer: Linear SNR = 20**

---

# 10. Signal-to-Noise Ratio (SNR)

SNR represents the ratio of useful signal power to noise power.

### Linear SNR Formula

`SNR = P_signal / P_noise`

Where:

- `P_signal` = signal power
- `P_noise` = noise power

---

## Numerical Example 9 — Linear SNR

Signal power = **500 W**  
Noise power = **0.5 W**

### Solution

`SNR = 500 / 0.5`

Since dividing by 0.5 is the same as multiplying by 2:

`SNR = 500 × 2`

`SNR = 1000`

**Answer: Linear SNR = 1000**

---

# 11. SNR in Decibels

SNR can also be expressed in decibels (dB).

### Formula

`SNR_dB = 10 × log10(SNR_linear)`

### Useful Values

- SNR = 1 → 0 dB
- SNR = 10 → 10 dB
- SNR = 100 → 20 dB
- SNR = 1000 → 30 dB

---

## Numerical Example 10 — SNR in dB

For a linear SNR of **100**, calculate SNR in dB.

### Solution

`SNR_dB = 10 × log10(100)`

`log10(100) = 2`

Therefore:

`SNR_dB = 10 × 2`

`SNR_dB = 20 dB`

**Answer: 20 dB**

---

# 12. Complete SNR Numerical

Signal power = **1000 W**  
Noise power = **10 W**

### Step 1 — Linear SNR

`SNR = 1000 / 10`

`SNR = 100`

### Step 2 — Convert to dB

`SNR_dB = 10 × log10(100)`

`SNR_dB = 20 dB`

**Final Answer:**

- Linear SNR = **100**
- SNR = **20 dB**

---

# 13. Basic RF Link Metrics

The main link metrics covered in this task are:

| Metric | Meaning |
|---|---|
| Frequency | Number of cycles per second |
| Time Period | Time required for one cycle |
| Bandwidth | Difference between upper and lower frequency |
| Center Frequency | Midpoint of the frequency range |
| Sampling Rate | Number of samples taken per second |
| Noise | Unwanted disturbance |
| SNR | Ratio of useful signal power to noise power |

---

# 14. Important Formulas — Quick Revision

### Frequency

`f = 1 / T`

### Time Period

`T = 1 / f`

### Bandwidth

`BW = f_high - f_low`

### Center Frequency

`f_c = (f_low + f_high) / 2`

### Nyquist Sampling Condition

`f_s >= 2 × f_max`

### Linear SNR

`SNR = P_signal / P_noise`

### SNR in dB

`SNR_dB = 10 × log10(SNR)`

---

# 15. Quick Conversion Shortcuts

### Frequency and Time Period

When frequency is in MHz and time period is in µs:

`T (µs) = 1 / f (MHz)`

Examples:

| Frequency | Time Period |
|---:|---:|
| 1 MHz | 1 µs |
| 2 MHz | 0.5 µs |
| 4 MHz | 0.25 µs |
| 5 MHz | 0.2 µs |
| 10 MHz | 0.1 µs |

### SNR

| Linear SNR | dB |
|---:|---:|
| 1 | 0 dB |
| 10 | 10 dB |
| 100 | 20 dB |
| 1000 | 30 dB |

---

# 16. Key Learning

The task established the basic RF and link-metric concepts required for the RF/DSP work. The study covered frequency, time period, bandwidth, center frequency, sampling, Nyquist sampling condition, noise, and SNR.

The numerical exercises provided practice in frequency/time conversion, bandwidth calculation, sampling-rate verification, and SNR calculation.

**Personal Expenditure: ₹0**

**Output File:** `rf_fundamentals_sheet.md`
