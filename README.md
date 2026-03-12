# Design-of-FIR-Filters-using-hanning-window

#DESIGN OF FIR DIGITAL FILTER 

# AIM: 
          
  To generate design of low pass FIR digital filter using SCILAB 

# APPARATUS REQUIRED: 

  PC Installed with SCILAB 

# PROGRAM 
```
clc;
close;

// Input values
M = input('Enter the Odd Filter Length = ');
Wc = input('Enter the Digital Cut off frequency = ');

alpha = (M-1)/2;   // Center Value

// Ideal Impulse Response
for n = 1:M
    if (n == alpha+1) then
        hd(n) = Wc/%pi;
    else
        hd(n) = sin(Wc*((n-1)-alpha)) / (%pi*((n-1)-alpha));
    end
end

// Hanning Window
for n = 1:M
    W(n) = 0.5 - 0.5*cos((2*%pi*(n-1))/(M-1));
end

// Windowing filter coefficients
h = hd .* W;

disp(h,'Filter Coefficients are');

// Frequency Response
[hzm,fr] = frmag(h,256);

subplot(2,1,1);
plot(2*fr,hzm);
xlabel('Normalized Digital Frequency w');
ylabel('Magnitude');
title('Frequency Response of FIR LPF using Hanning Window');

// Magnitude in dB
hzm_dB = 20*log10(hzm);

subplot(2,1,2);
plot(2*fr,hzm_dB);
xlabel('Normalized Digital Frequency W');
ylabel('Magnitude in dB');
title('Frequency Response of FIR LPF using Hanning Window');
```

# OUTPUT
<img width="1342" height="813" alt="image" src="https://github.com/user-attachments/assets/f303c92e-5a82-41e3-a880-acad3c7bbd68" />

# RESULT
To generate design of low pass FIR digital filter using SCILAB  is verified
