# DSP-LAB-3

#LINEAR CONVOLUTION USING FFT

PROGRAM:

clc;
clear all;
close all;
x=input('Enter the first input sequence x(n):');
h=input('Enter the second input sequence h(n):');
n1=length(x);
n2=length(h);
n=n1+n2-1;
X=fft(x,n);
H=fft(h,n);
Y=X.*H;
y=ifft(Y);
disp('linear convolution output is:');
disp(y);
t1=0:n1-1;
subplot(1,3,1);
stem(t1,x);
xlabel('n');
ylabel('Amplitude');
title('first input sequence');
t2=0:n2-1;
subplot(1,3,2);
stem(t2,h);
xlabel('n');
ylabel('Amplitude');
title('second input sequence');
t=0:1:n-1;
subplot(1,3,3);
stem(t,y);
xlabel('n');
ylabel('Amplitude');
title('output sequence');
