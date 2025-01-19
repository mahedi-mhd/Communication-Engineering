# Communication-Engineering
Matlab program for Communication Engineering

1.A Program To graphically Represent a sinusoidal function in both time Domain and Frequency Domain

fs=2000;
t=0:1/fs:.25;
f1 =10;
f2=50;
f3=100;
v1=20*sin (2*pi*f1*t); 
v2=20*sin (2*pi*f2*t); 
v3=20*sin (2*pi*f3*t); 
v=v1+v2+v3;

subplot (2, 1, 1);
plot(t, v);
title ('Time domain');
xlabel ('Time');
ylabel ('Amplitude');
N=256;
Y=fft (v, N) ;
V=abs (Y).^2/N;
f=fs* (0: N-1) /N;
subplot (2,1,2);
plot (f, V);
title('Frequency domain');
xlabel('Frequency');
ylabel('Amplitude');


2.Fourier Transform a sine wave function and Plot graph using Matlab

f=30;
fs=100;
t=0:1/fs:1;
x=sin (2*f*t) ;
subplot (2,1,1);
plot (t, x);
title('sin wave');
xlabel ('amplitude');
n=1024;
y=fft (x, n) ;
f=(fs/n) * (((-n/2): ((n/2)-1)));
subplot (2, 1, 2);
plot (f, abs (y));
title ('FFT of sin wave');
xlabel('frequency...>'); 
ylabel('amplitude...>');

3.write a matlab Program to quantize a Signal

t= 0:0.001:1;
fn=10;
x=sin (2*pi*fn*t);
subplot (2, 1, 1);
plot(t, x);
title ("sinewave [main Signal]"); 
xlabel('time');
ylabel('amplitude');
Vmin=-1;
Vmax=1;
level=input('Enter level='); 
del = (Vmax-Vmin) /level; 
partition= Vmin: del: Vmax; 
codebook=(Vmin-del): del: Vmax;
[ind, q] = quantiz (x, partition, codebook) ;
subplot (2,1,2);
plot(t,q);
title('Quantiz');
xlabel('Time');
ylabel('Amplitude');
 

4.write a matlab program for delta modulation

t=0:0.01:1; 
fm=5;
x=2*cos (2*pi*fm*t);
subplot (2,1,1)
 plot (t, x)
title('message signal')
xlabel('time')
ylabel('x')
s=[0];
n=1;
while (n<=100)
if (x (n)>s (1))
s(1) =s (1) +1;
else
s (1)= s (1) -1;
end
n=n+1;
z (n) =s (1);
end
subplot (2,1,2)
plot (t, z)
title('delta modulation signal')
xlabel('time')
ylabel('z')




