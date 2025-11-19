# DSBSC-using-PYTHON
AIM

To implement and analyze Double Sideband Suppressed Carrier (DSB-SC) modulation using Python's NumPy and Matplotlib libraries.

APPARATUS REQUIRED

Software: Python with NumPy and Matplotlib libraries
Hardware: Personal Computer

THEORY

Double Sideband Suppressed Carrier (DSB-SC) modulation is a type of amplitude modulation in which the carrier is completely suppressed, and only the sidebands containing the message information are transmitted.
Unlike conventional AM, the transmitted power in DSB-SC is concentrated in the sidebands, making it more power efficient. The modulated signal is obtained by multiplying the carrier and message signals directly.

Mathematically,

𝑠
(
𝑡
)
=
𝑚
(
𝑡
)
⋅
cos
⁡
(
2
𝜋
𝑓
𝑐
𝑡
)
s(t)=m(t)⋅cos(2πf
c
	​

t)

where

𝑚
(
𝑡
)
=
𝐴
𝑚
cos
⁡
(
2
𝜋
𝑓
𝑚
𝑡
)
m(t)=A
m
	​

cos(2πf
m
	​

t) is the message signal,

𝑓
𝑐
f
c
	​

 is the carrier frequency, and

𝑠
(
𝑡
)
s(t) is the DSB-SC modulated signal.

ALGORITHM

Initialize Parameters: Set values for carrier frequency, message frequency, amplitude, and sampling frequency.

Generate Time Axis: Create a time vector for the duration of two message signal cycles.

Generate Message Signal: Define the message signal as a cosine wave.

Generate Carrier Signal: Define the carrier signal as a high-frequency cosine wave.

Generate DSB-SC Signal: Multiply the message signal with the carrier signal to produce the DSB-SC waveform.

Plot Results: Display the message, carrier, and modulated signals using Matplotlib.

PROGRAM

```
import numpy as np
import matplotlib.pyplot as plt

am = 4.2
fm = 368
ac = 8.4
fc = 3680
fs = 36800
beta = 3.3
t = np.arange(0, 2/fm, 1/fs)

m = am * np.cos(2 * np.pi * fm * t)
plt.subplot(3, 1, 1)
plt.plot(t, m)
plt.title("Message Signal (m(t))")
plt.xlabel("Time (s)")
plt.ylabel("Amplitude")

c = ac * np.cos(2 * np.pi * fc * t)
plt.subplot(3, 1, 2)
plt.plot(t, c)
plt.title("Carrier Signal (c(t))")
plt.xlabel("Time (s)")
plt.ylabel("Amplitude")

dsbsc_signal = m * c
plt.subplot(3, 1, 3)
plt.plot(t, dsbsc_signal)
plt.title("DSBSC Signal")
plt.xlabel("Time (s)")
plt.ylabel("Amplitude")

plt.tight_layout()
plt.show()
```

OUTPUT WAVEFORM

<img width="630" height="469" alt="image" src="https://github.com/user-attachments/assets/495cc141-0e8f-4dfc-803e-f6a34443f0b3" />


TABULAR COLUMN
<img width="960" height="1280" alt="image" src="https://github.com/user-attachments/assets/d19f7f7d-3880-460d-bcf7-1f3db175ffbb" />



<img width="630" height="469" alt="image" src="https://github.com/user-attachments/assets/857fcb74-1b1f-4fe2-a33b-10d58362a469" />

RESULT
The message signal, carrier signal, and DSB-SC modulated signal were successfully generated and plotted using Python.
The resulting waveform verifies that the carrier component is suppressed and only the sidebands are transmitted, demonstrating the Double Sideband Suppressed Carrier modulation technique.
