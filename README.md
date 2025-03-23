# Exp:1 Ideal Sampling
# Name: Gowri Sankari R
# Reg no: 212223060073

### AIM:

To demonstrate ideal sampling of a continuous signal using Scilab, ensuring accurate signal reconstruction while avoiding aliasing

### COMPONENTS REQUIRED:

Python IDE with numpy and scipy

### PROGRAM:

```PYTHON
import numpy as np
import matplotlib.pyplot as plt
from scipy.signal import resample
fs = 100
t = np.arange(0, 1, 1/fs) 
f = 5
signal = np.sin(2 * np.pi * f * t)
plt.figure(figsize=(10, 4))
plt.plot(t, signal, label='Continuous Signal')
plt.title('Continuous Signal (fs = 100 Hz)')
plt.xlabel('Time [s]')
plt.ylabel('Amplitude')
plt.grid(True)
plt.legend()
plt.show()
t_sampled = np.arange(0, 1, 1/fs)
signal_sampled = np.sin(2 * np.pi * f * t_sampled)
plt.figure(figsize=(10, 4))
plt.plot(t, signal, label='Continuous Signal', alpha=0.7)
plt.stem(t_sampled, signal_sampled, linefmt='r-', markerfmt='ro', basefmt='r-', label='Sampled Signal (fs = 100 Hz)')
plt.title('Sampling of Continuous Signal (fs = 100 Hz)')
plt.xlabel('Time [s]')
plt.ylabel('Amplitude')
plt.grid(True)
plt.legend()
plt.show()
reconstructed_signal = resample(signal_sampled, len(t))
plt.figure(figsize=(10, 4))
plt.plot(t, signal, label='Continuous Signal', alpha=0.7)
plt.plot(t, reconstructed_signal, 'r--', label='Reconstructed Signal (fs = 100 Hz)')
plt.title('Reconstruction of Sampled Signal (fs = 100 Hz)')
plt.xlabel('Time [s]')
plt.ylabel('Amplitude')
plt.grid(True)
plt.legend()
plt.show()
```

### OUTPUT WAVEFORM:

![image](https://github.com/user-attachments/assets/85fb1c64-43d1-4877-aedf-e90ad5db15cd)

![image](https://github.com/user-attachments/assets/6b115f89-c286-4a34-ae08-2671fc0f4f43)

![image](https://github.com/user-attachments/assets/700039e3-aba7-4ff2-b664-47fb5632c21a)

### RESULT:

Ideal sampling captures a continuous signal at perfect intervals, ensuring accurate
reconstruction if sampled at twice the highest frequency (Nyquist rate). It’s a key
concept in digital signal processing and telecommunications. Practical systems
approximate ideal sampling with some limitations.

