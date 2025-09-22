# EXP 1 A : COMPUTATION OF DFT USING DIRECT AND FFT

# AIM: 

# To Obtain DFT and FFT of a given sequence in SCILAB. 

# APPARATUS REQUIRED: 
PC installed with SCILAB. 

# PROGRAM: 
```clc;
clear;


x = input("Enter discrete signal as [x1 x2 ...]: ");
N = length(x);

X_dft = zeros(1, N);
for k = 0:N-1
    for n = 0:N-1
        X_dft(k+1) = X_dft(k+1) + x(n+1) * exp(-%i * 2 * %pi * k * n / N);
    end
end


f = (0:N-1) / N;


scf(0);
subplot(2,1,1);
plot2d3(f, abs(X_dft));
xtitle("Magnitude Spectrum using Direct DFT");

subplot(2,1,2);
plot2d3(f, atan(imag(X_dft), real(X_dft)));
xtitle("Phase Spectrum using Direct DFT");


X_fft = fft(x, -1);


scf(1);
subplot(2,1,1);
plot2d3(f, abs(X_fft));
xtitle("Magnitude Spectrum using FFT");

subplot(2,1,2);
plot2d3(f, atan(imag(X_fft), real(X_fft)));
xtitle("Phase Spectrum using FFT");
```
# OUTPUT: 
<img width="920" height="740" alt="Screenshot 2025-09-22 035124" src="https://github.com/user-attachments/assets/f11508aa-5144-4e5d-9eec-82f3f018242e" />


# RESULT: 
Hence DFT signal is simulated using FFT
