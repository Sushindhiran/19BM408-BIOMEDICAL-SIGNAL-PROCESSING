# ECG Signal Analysis and QRS Detection using MATLAB
# AIM:

To analyze an ECG signal and detect QRS complexes using MATLAB.

# THEORY:

Electrocardiography (ECG) is a diagnostic technique used to measure the electrical activity of the heart. The ECG signal is generated due to the depolarization and repolarization of cardiac muscle cells during each heartbeat.
A typical ECG waveform consists of several components:

•	P wave – atrial depolarization

•	QRS complex – ventricular depolarization

•	T wave – ventricular repolarization

Among these components, the QRS complex has the highest amplitude and is the most significant feature used for detecting heart rate and cardiac abnormalities.
ECG signals are often affected by noise such as:

•	baseline wander

•	muscle noise

•	power-line interference (50 Hz)

Signal processing techniques are used to filter noise and extract useful features from ECG signals. One important technique is QRS detection, which identifies the location of ventricular depolarization peaks.
MATLAB provides functions such as findpeaks() that help detect QRS complexes automatically. Detecting QRS peaks allows biomedical engineers and doctors to calculate heart rate and identify arrhythmias.

# ALGORITHM :
1.	Load ECG signal data.
2.	Define the sampling frequency.
3.	Plot the ECG signal waveform.
4.	Apply a threshold-based method to detect QRS peaks.
5.	Mark the detected peaks on the ECG signal.
6.	Display the result.

# MATLAB CODE :
```
clc;
clear;
close all;

S = load("ecg.mat");

vars = fieldnames(S);
ecg = S.(vars{1}); 

ecg = ecg(:); 

fs = 360;
t = (0:length(ecg)-1)/fs;

figure;
plot(t, ecg);
hold on;

[pks, locs] = findpeaks(ecg, 'MinPeakHeight', 0.5);

plot(locs/fs, pks, 'ro', 'MarkerFaceColor', 'r');

xlabel('Time (seconds)');
ylabel('Amplitude');
title('ECG Signal with QRS Detection');
legend('ECG Signal', 'Detected Peaks');
grid on;
```
# OUTPUT GRAPH :

<img width="758" height="608" alt="BSPEXP12FIG1" src="https://github.com/user-attachments/assets/4555fe00-acaa-4f7e-91ee-fdc152ba0ba5" />

# RESULT :
The ECG signal was analyzed and QRS complexes were successfully detected using MATLAB.

