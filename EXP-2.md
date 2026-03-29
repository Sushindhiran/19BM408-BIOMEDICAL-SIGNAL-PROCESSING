# COMPUTATION OF DISCRETE FOURIER TRANSFORM (DFT) OF A DISCRETE-TIME SIGNAL
#  Aim :
To compute and plot the Discrete Fourier Transform (DFT) of a given discrete-time signal using MATLAB.
# Apparatus / Software Required:
•	Computer / Laptop

•	MATLAB software
# Theory :
A discrete-time signal may contain multiple frequency components.
The Discrete Fourier Transform (DFT) converts a signal from the time domain into the frequency domain and shows the strength of each frequency present in the signal.
MATLAB computes DFT efficiently using the Fast Fourier Transform (FFT) algorithm.

Mathematical Expression:
X(k)=∑_(n=0)^(N-1)▒〖x(n)" " 〗 e^(-j2πkn/N)

Where:
	x(n)→ input signal.
  X(k)→ frequency spectrum.
  N→ number of samples.

# Algorithm :
	1) Start the program
	2) Define the discrete-time signal x(n)
	3) Find the length of the signal
	4) Compute the DFT using fft()
	5) Calculate magnitude spectrum using abs()
	6) Plot the DFT using stem()
	7)Stop the program

# MATLAB CODE :

```
clc;
clear;
close all;
x = [1 1 1 1];
N = length(x);
X = fft(x);
disp('DFT of the given signal is:');
disp(X);
k = 0:N-1;
figure;
stem(k, abs(X), 'filled');
xlabel('Frequency index k');
ylabel('|X(k)|');
title('Magnitude Spectrum of DFT');
grid on;
```

# OUTPUT GRAPH :

<img width="741" height="608" alt="BSPEXP2FIG1" src="https://github.com/user-attachments/assets/861e0e4b-06f2-49bd-8962-f0da4999ee8d" />

# Result :
Thus, the Discrete Fourier Transform of the given discrete-time signal was successfully computed and plotted using MATLAB.



