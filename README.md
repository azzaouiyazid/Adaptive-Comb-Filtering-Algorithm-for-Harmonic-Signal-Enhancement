# Adaptive Comb Filtering Algorithm for Harmonic Signal Enhancement
This project implements an adaptive comb filtering algorithm for the enhancement of harmonic signals in the presence of additive white noise. The algorithm consists of two cascaded parts: the first estimates the fundamental frequency and enhances the harmonic component in the input, while the second estimates the harmonic amplitudes and phases. The performance of the algorithm is analyzed through the calculation of the asymptotic Cramer-Rao bound (CRB) on the parameters of the harmonic signals. Simulations are carried out to compare the variances of the estimates to the CRB, and to demonstrate the ability of the algorithm to enhance noisy artificial periodic signals.

# Usage
The main function of the project is adaptive_comb_filter(signal, fs, f0, alpha). It takes as input:

signal: the input signal to be filtered.<br>
fs: the sampling frequency of the input signal.<br>
f0: the estimated fundamental frequency of the harmonic signal.<br>
alpha: the filter coefficient, between 0 and 1.<br>
It returns the filtered signal.

Here's an example of how to use the function:

```python
import numpy as np
from adaptive_comb_filter import adaptive_comb_filter
```

# Set the parameters

fs = 44100 # Sampling frequency<br>
f0 = 1000 # Fundamental frequency<br>
alpha = 0.9 # Filter coefficient

# Generate a synthetic harmonic signal with additive white noise
t = np.linspace(0, 1, fs)<br>
signal = np.sin(2*np.pi*f0*t) + 0.1*np.random.randn(len(t))

# Enhance the signal using the adaptive comb filter
filtered_signal = adaptive_comb_filter(signal, fs, f0, alpha)

You can also plot the original and filtered signal like this

```python
import matplotlib.pyplot as plt
plt.plot(t, signal)
plt.plot(t, filtered_signal)
plt.show()
```
The output will look like this :

![Screenshot 2023-01-07 143052](https://user-images.githubusercontent.com/78693054/211544936-2ee3390d-6e03-499d-8fe1-682fbf1bd104.png)

As shown in the above image, the filtered signal is an enhanced version of the input signal with reduced noise.

# Conclusion :
This adaptive comb filtering algorithm is able to effectively enhance harmonic signals in the presence of additive white noise. The performance of the algorithm is analyzed through the calculation of the asymptotic Cramer-Rao bound (CRB) on the parameters of the harmonic signals. Simulations are carried out to compare the variances of the estimates to the CRB, and to demonstrate the ability of the algorithm to enhance noisy artificial periodic signals.
