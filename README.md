# Design-of-FIR-Filters-using-rectangular-window
#          DESIGN OF LOW PASS FIR DIGITAL FILTER 

# AIM: 
          
  To generate design of low pass FIR digital filter using SCILAB 

# APPARATUS REQUIRED: 

  PC Installed with SCILAB 

# PROGRAM 
```
clc;
clear;
close;

// Filter specifications
N = 21;          // Filter length
fc = 0.12;       // Normalized cutoff frequency (0 < fc < 0.5)
M = N - 1;
n = 0:M;

// Ideal impulse response (sinc function)
hd = 2 * fc * sinc(2 * fc * (n - M/2));

// Rectangular window
w = ones(1, N);

// FIR filter coefficients
h = hd .* w;

// Frequency response
[H, f] = frmag(h, 1024);   // magnitude response

// ---- Plot impulse response (use plot2d3 instead of stem) ----
figure(1);
plot2d3(n, h);
title('Impulse Response of FIR Low Pass Filter (Rectangular Window)');
xlabel('n');
ylabel('h[n]');
xgrid();

// ---- Plot magnitude response ----
figure(2);
plot(f, abs(H));
title('Magnitude Response');
xlabel('Normalized Frequency');
ylabel('|H(f)|');
xgrid();

// ---- Display filter coefficients ----
disp("Filter Coefficients (h[n]):");
disp(h');

disp("Filter length (N): " + string(N));
disp("Cutoff frequency (fc): " + string(fc));
disp("Window used: Rectangular");
```

# OUTPUT
<img width="1204" height="597" alt="image" src="https://github.com/user-attachments/assets/0c3c51c5-0de6-4cb9-aa2b-19842b0c3558" />
<img width="1161" height="563" alt="image" src="https://github.com/user-attachments/assets/70e89798-2662-46f2-864d-28ed3672a40b" />
<img width="365" height="463" alt="image" src="https://github.com/user-attachments/assets/183808a7-d763-4905-aea3-2bc86c337230" />


# RESULT
design of low pass FIR digital filter using SCILAB is generated

