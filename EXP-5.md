# DESIGN OF DIGITAL BUTTERWORTH LOW PASS FILTER USING BILINEAR TRANSFORMATION
# Aim:

To design a digital Butterworth low pass filter using the bilinear transformation method in MATLAB satisfying the given constraints:

0.707≤∣H(ω)∣≤1.0;0≤ω≤0.2π

∣H(ω)∣≤0.08;0.4π≤ω≤π

Assume sampling period T=1second.

# APPARATUS REQUIRED :
MATLAB software
Computer system

Given Specifications

Passband edge frequency:

ω_p=0.2π

Stopband edge frequency:

ω_s=0.4π

Passband ripple:

A_p=-20〖log⁡〗_10 (0.707)=3" dB"

Stopband attenuation:

A_s=-20〖log⁡〗_10 (0.08)≈21.94" dB"

Sampling period:

T=1" second"

# THEORY :
The Butterworth filter is a maximally flat magnitude filter with no ripples in the passband and stopband.
The bilinear transformation converts an analog filter into a digital filter using the relation:

s=2/T  (1-z^(-1))/(1+z^(-1) )

Frequency pre-warping is done to compensate for frequency distortion introduced by bilinear transformation.
The steps involved are:

1)Prewarp digital frequencies to analog frequencies.  

2)Design analog Butterworth filter.
  
3)Convert analog filter into digital filter using bilinear transformation.
  
4)Plot magnitude and phase response.

# ALGORITHM :

1.	Specify passband and stopband edge frequencies.
2.	Convert digital frequencies to analog frequencies using pre-warping.
3.	Compute filter order and cutoff frequency using Butterworth approximation.
4.	Design analog Butterworth low pass filter.
5.	Convert analog filter into digital filter using bilinear transformation.
6.	Plot frequency response using freqz.
7.	Verify whether the filter satisfies the given constraints.

# MATLAB CODE :
```
clc;
clear;
close all;
T = 1;
wp = 0.2*pi;
ws = 0.4*pi;
Ap = 3;
As = 21.94;
Wp = (2/T)*tan(wp/2);
Ws = (2/T)*tan(ws/2);
[N, Wn] = buttord(Wp, Ws, Ap, As, 's');
[b, a] = butter(N, Wn, 's');
[bd, ad] = bilinear(b, a, 1/T);
[H, w] = freqz(bd, ad, 1024);
figure;
plot(w/pi, abs(H));
grid on;
xlabel('Normalized Frequency (\times\pi rad/sample)');
ylabel('Magnitude');
title('Magnitude of Butterworth LPF');
figure;
plot(w/pi, angle(H));
grid on;
xlabel('Normalized Frequency (\times\pi rad/sample)');
ylabel('Phase (radians)');
title('Phase angle of Butterworth LPF');
```

# OUTPUT GRAPH :

<img width="743" height="607" alt="BSPEXP5FIG1" src="https://github.com/user-attachments/assets/e1f09ac4-9148-405c-9f9f-67f556a504e1" />
<img width="733" height="607" alt="BSPEXP5FIG2" src="https://github.com/user-attachments/assets/cde7c49e-3223-4459-98e4-41bbd591ee08" />

# RESULT:
A digital Butterworth low pass filter satisfying the given constraints was successfully designed using the bilinear transformation method and its frequency response was verified using MATLAB.



