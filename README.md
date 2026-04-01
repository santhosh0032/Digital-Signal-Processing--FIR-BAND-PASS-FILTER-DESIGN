# Digital-Signal-Processing--FIR-BAND-PASS-FILTER-DESIGN
## AIM:
To generate design of Band Pass FIR digital filter using Window.
## Software Required:
MAT LAB R2012.
## Algorithm:
Step 1: Open MATLAB and Write the program.

Step 2: Read the values of cut off frequency wc.

Step 2: Read the values of Order of the filter N.

Step 3: Find out the desired impulse response of the Band Pass filter Coefficient.

Step 4: Find out the windowing sequence.

Step 5: Plot the magnitude spectrum with x-label and y-label with suitable title.

Step 6: Terminate the program.

## PROGRAM: 
~~~
clc; % clear screen
clear all; % clear workspace
close all; % close all figure windows

Wc1 = input('enter the value of Wc1=');
Wc2 = input('enter the value of Wc2=');
N = input('enter the value of N=');

alpha = (N-1)/2;
eps = 0.001;

% Band Pass Filter Coefficient
n = 0:1:N-1;
hd = (sin(Wc2*(n-alpha+eps)) - sin(Wc1*(n-alpha+eps))) ./ ((n-alpha+eps)*pi);

% Blackman Window Sequence
n = 0:1:N-1;
wh = 0.42 - 0.5*cos((2*pi*n)/(N-1)) + 0.08*cos((4*pi*n)/(N-1));

% Windowed impulse response
hn = hd .* wh;

% Plot the Band Pass Filter with Blackman window Technique
w = 0:0.01:pi;
h = freqz(hn,1,w);

plot(w/pi, abs(h), 'black');
xlabel('Normalized Frequency');
ylabel('Magnitude');
title('Band Pass Filter using Blackman Window');
grid on;
~~~

## OUTPUT:
![WhatsApp Image 2026-04-01 at 11 39 08 AM](https://github.com/user-attachments/assets/e1b8d295-8612-49f8-b01f-86be065dc603)

## RESULT:
![WhatsApp Image 2026-04-01 at 10 32 20 PM](https://github.com/user-attachments/assets/8e66f42c-f469-44a3-8b30-edd0186e927e)

