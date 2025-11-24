### Design-of-FIR-Filters-using-hamming-window
### DESIGN OF LOW PASS FIR DIGITAL FILTER 
Name: Namachivayam T

Reg No: 212223060179

### AIM:       
  To generate design of high pass FIR digital filter using SCILAB 

### APPARATUS REQUIRED: 
  PC Installed with SCILAB 

### PROGRAM 
//LPF
```
clc;
clear;
close;

M = input('Enter the Odd Filter Length = ');
Wc = input('Enter the Digital Cut off frequency (in radians) = ');

alpha = (M - 1) / 2; // Center value

// Ideal Low Pass filter coefficients
for n = 1:M
    if (n == alpha + 1) then
        hd(n) = Wc / %pi;   // center tap
    else
        hd(n) = sin(Wc * ((n - 1) - alpha)) / (((n - 1) - alpha) * %pi);
    end
end

// Hamming Window
for n = 1:M
    W(n) = 0.54 - (0.46 * cos((2 * %pi * (n - 1)) / (M - 1)));
end

// Apply window to ideal filter
h = hd .* W;
disp(h, 'Filter Coefficients are:');

// Frequency response
[hzm, fr] = frmag(h, 256);

subplot(2, 1, 1);
plot(2 * fr, hzm);
xlabel('Normalized Digital Frequency w');
ylabel('Magnitude');
title('Frequency Response of FIR LPF using Hamming Window');

hzm_dB = 20 * log10(hzm);
subplot(2, 1, 2);
plot(2 * fr, hzm_dB);
xlabel('Normalized Digital Frequency w');
ylabel('Magnitude (dB)');
title('Frequency Response of FIR LPF using Hamming Window');

```
//HPF
```
clc;
clear;
close;

M = input('Enter the Odd Filter Length = ');
Wc = input('Enter the Digital Cut off frequency (in radians) = ');

alpha = (M - 1) / 2; // Center value

// Ideal High Pass filter coefficients
for n = 1:M
    if (n == alpha + 1) then
        hd(n) = 1 - (Wc / %pi);
    else
        hd(n) = -sin(Wc * ((n - 1) - alpha)) / (((n - 1) - alpha) * %pi);
    end
end

// Hamming Window
for n = 1:M
    W(n) = 0.54 - (0.46 * cos((2 * %pi * (n - 1)) / (M - 1)));
end

// Apply window to ideal filter
h = hd .* W;
disp(h, 'Filter Coefficients are:');

// Frequency response
[hzm, fr] = frmag(h, 256);

subplot(2, 1, 1);
plot(2 * fr, hzm);
xlabel('Normalized Digital Frequency w');
ylabel('Magnitude');
title('Frequency Response of FIR HPF using Hamming Window');

hzm_dB = 20 * log10(hzm);
subplot(2, 1, 2);
plot(2 * fr, hzm_dB);
xlabel('Normalized Digital Frequency w');
ylabel('Magnitude (dB)');
title('Frequency Response of FIR HPF using Hamming Window');

```

### OUTPUT
<img width="922" height="616" alt="FIR-hamming HPF" src="https://github.com/user-attachments/assets/61466ca1-b0e3-41a3-b6c9-327bf12e87fc" />
<img width="864" height="584" alt="FIR-hamming LPF" src="https://github.com/user-attachments/assets/cc18af36-e7e2-4a23-83a6-7c50e7c7ef18" />

### RESULT
Design-of-FIR-Filters-using-hanning-window using SCILAB executed successfully.
