# GENERATION OF STANDARD DISCRETE-TIME SIGNALS
# AIM:
To generate and plot standard discrete-time signals using MATLAB.
# APPARATUS REQUIRED:
•	Computer / Laptop
•	MATLAB software
# THEORY:
Discrete-time signals are signals defined only at integer values of time (n).
These signals are basic building blocks in Digital Signal Processing (DSP) and are used for system analysis, filtering, and signal modeling.
Standard discrete-time signals include:
	Unit Impulse
	Unit Step
	Ramp
	Exponential
	Sinusoidal
	Damped Sinusoidal
In MATLAB, discrete-time signals are represented using vectors and plotted using the stem() command.
 Standard Discrete-Time Signals
 
🔹 1. Unit Impulse Signal
δ(n)={■(1,&n=0@0,&n≠0)┤

🔹 2. Unit Step Signal
u(n)={■(1,&n≥0@0,&n<0)┤

🔹 3. Ramp Signal
r(n)=n⋅u(n)

🔹 4. Exponential Signal
x(n)=a^n

🔹 5. Sinusoidal Signal
x(n)=sin⁡(ωn)

🔹 6. Damped Sinusoidal Signal
x(n)=a^n sin⁡(ωn)

# ALGORITHM:
1.	Start the program
2.	Define the sample index n
3.	Generate each standard discrete-time signal
4.	Plot the signal using stem()
5.	Label the axes and title
6.	Stop the program

# MATLAB CODE:

```
% GENERATION OF STANDARD DISCRETE-TIME SIGNALS

clc;
clear;
close all;

%% Sample index
n = -10:10;

%% 1. Unit Impulse Signal
x1 = (n == 0);
figure;
stem(n, x1, 'filled');
title('Unit Impulse Signal');
xlabel('n'); ylabel('Amplitude');
grid on;

%% 2. Unit Step Signal
x2 = (n >= 0);
figure;
stem(n, x2, 'filled');
title('Unit Step Signal');
xlabel('n'); ylabel('Amplitude');
grid on;

%% 3. Ramp Signal
n1 = 0:10;
x3 = n1;
figure;
stem(n1, x3, 'filled');
title('Ramp Signal');
xlabel('n'); ylabel('Amplitude');
grid on;

%% 4. Exponential Signal
a = 0.8;
x4 = a.^n1;
figure;
stem(n1, x4, 'filled');
title('Exponential Signal');
xlabel('n'); ylabel('Amplitude');
grid on;

%% 5. Sinusoidal Signal
x5 = sin(0.3*pi*n1);
figure;
stem(n1, x5, 'filled');
title('Sinusoidal Signal');
xlabel('n'); ylabel('Amplitude');
grid on;

%% 6. Damped Sinusoidal Signal
x6 = (0.9.^n1).*sin(0.4*pi*n1);
figure;
stem(n1, x6, 'filled');
title('Damped Sinusoidal Signal');
xlabel('n'); ylabel('Amplitude');
grid on;
```

# OUTPUT GRAPH:

<img width="748" height="603" alt="BSPEXP1FIG6" src="https://github.com/user-attachments/assets/ce725f2d-c051-4157-93b4-352d49afaa90" />
<img width="741" height="603" alt="BSPEXP1FIG1" src="https://github.com/user-attachments/assets/8cb0b202-e40e-497d-82db-bee1f1e87874" />
<img width="741" height="603" alt="BSPEXP1FIG2" src="https://github.com/user-attachments/assets/3669f984-b0e3-418d-876f-05a47f9efe37" />
<img width="736" height="603" alt="BSPEXP1FIG3" src="https://github.com/user-attachments/assets/81e891aa-9425-4650-ab5d-b0f198ddceb3" />
<img width="741" height="603" alt="BSPEXP1FIG4" src="https://github.com/user-attachments/assets/fdaf9c21-e7e4-44c5-a3d8-b37a957dd713" />
<img width="748" height="603" alt="BSPEXP1FIG5" src="https://github.com/user-attachments/assets/d75330a9-0946-453d-8b68-7fbf078e3b3a" />


# Result :
Thus, standard discrete-time signals were successfully generated and plotted using MATLAB.



