# HANNING WINDOW BASED FIR FILTER DESIGN

# AIM:

To design a Low Pass FIR filter using Hanning (Hann) Window and analyze its response.
# THEORY :

Hanning window is defined as:

w(n)=0.5-0.5cos⁡(2πn/N)

Characteristics:

1)Smooth tapering at ends

2)Reduced spectral leakage

3)Moderate stopband attenuation (~31 dB)

4)Wider main lobe than Hamming

Design Equation:

h(n)=h_d (n)⋅w(n)

# ALGORITHM :
1.	Select N and ωc
2.	Compute ideal response
3.	Generate Hanning window
4.	Multiply and obtain FIR coefficients
5.	Plot response

# MATLAB CODE :

```
clc;
clear;
close all;

N = 20;
wc = 0.4*pi;
n = 0:N;
alpha = N/2;

hd = sin(wc*(n-alpha))./(pi*(n-alpha));
hd(alpha+1) = wc/pi;

w = hann(N+1)';
h = hd.*w;

freqz(h,1);
title('FIR using Hanning Window');
```

# OUTPUT GRAPH :

<img width="739" height="301" alt="BSPEXP9FIG1" src="https://github.com/user-attachments/assets/3ca4f129-3e4e-4b0a-9c49-ebffa086f68d" />
<img width="768" height="305" alt="BSPEXP9FIG2" src="https://github.com/user-attachments/assets/c13c7493-4d57-4ab5-9578-49370e95de49" />

DIF-FFT Output:
  20.0000 + 0.0000i  -5.8284 - 2.4142i   0.0000 + 0.0000i  -0.1716 - 0.4142i   0.0000 + 0.0000i  -0.1716 + 0.4142i   0.0000 + 0.0000i  -5.8284 + 2.4142i

# RESULT :
The FIR filter was designed using Hanning window.
