# Experiment 1

## MATLAB code
clc;
clear;
Fs = 10000;
Fp = 1000;
Fst = 1500;
[N,Wn] = buttord(Fp/(Fs/2), Fst/(Fs/2), 1, 60);
[b,a] = butter(N,Wn);
% Figure 1 - Frequency Response
figure(1);
freqz(b,a);
% Figure 2 - Impulse Response
figure(2);
impz(b,a,50);
title('Impulse Response');
% Figure 3 - Step Response
figure(3);
stepz(b,a);
title('Step Response');
% Figure 4 - Pole-Zero Plot
figure(4);
zplane(b,a);
title('Pole-Zero Plot');
fprintf('Minimum Filter Order (N) = %d\n', N);
fprintf('Cutoff Frequency (Wn) = %.4f\n', Wn);

## Output figures

### Figure 1
![Figure 1](Figure1.png)
### Figure 2
![Figure 2](Figure2.png)
### Figure 3
![Figure 3](Figure3.png)
### Figure 4
![Figure 4](Figure4.png)
