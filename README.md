### Design-of-FIR-Filters-using-hanning-window
### DESIGN OF FIR DIGITAL FILTER 

### AIM:         
  To generate design of low pass FIR digital filter using SCILAB 

### APPARATUS REQUIRED: 
  PC Installed with SCILAB 

### PROGRAM 
```
clc ; 
close ; 
M=input('Enter the Odd Filter Length ='); 
Wc=input('Enter the Digital Cut off frequency ='); 
alpha= (M -1)/2 // Center Value 
for n = 1:M 
if (n ==alpha+1) 
hd(n) = Wc/ %pi ; 
else 
hd(n) = sin(Wc *((n -1)-alpha)) /(((n -1)-alpha)*%pi); 
end 
end 
// hanning Window 
for n = 1:M 
W(n) = 0.5-(0.5*cos((2*%pi*(n-1))/(M-1))); 
end 
//Windowing filter coefficients 
h = hd.*W; 
disp(h,'Filter Coefficients are') 
[hzm,fr]= frmag (h,256) ; 
subplot(2 ,1 ,1) 
plot(2*fr, hzm) 
xlabel( ' Normalized Digital Frequency w'); 
ylabel( 'Magnitude '); 
title( ' Frequency Response of  FIR LPF using Hanning Window ') 
hzm_dB = 20* log10 (hzm); 
subplot (2 ,1 ,2); 
plot(2*fr , hzm_dB); 
xlabel( ' Normalized Digital Frequency W' ); 
ylabel( 'Magnitude in dB');  
title('Frequency Response of FIR LPF using Hanning Window');
```

### OUTPUT
<img width="1920" height="1080" alt="Screenshot (152)" src="https://github.com/user-attachments/assets/3270c99f-a46d-4c39-8b87-5294503bd808" />

<img width="1920" height="1080" alt="Screenshot (153)" src="https://github.com/user-attachments/assets/bc9e7f74-8e8e-450f-be83-073a304a11b5" />

### RESULT
Design-of-FIR-Filters-using-hanning-window using SCILAB executed successfully.
