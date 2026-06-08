# FIR-FILTER-DESIGN
# EXP 4 d: Design-of-FIR-Digital-Filter-using-Blackman-Window

# AIM 1:  To perform Design-of-LOWPASS FIR-Digital-Filter-using-Blackman-Window using SCILAB.

# APPARATUS REQUIRED: 
PC installed with SCILAB. 

# PROGRAM: 
~~~
clc ; 
close ; 
M=input('Enter the Odd Filter Length ='); 
Wc=input('Enter the Digital Cut off frequency ='); 
alpha= (M -1)/2 // Center Value 
for n = 1:M 
if (n ==alpha+1) 
hd(n) = Wc/ %pi ; else 
hd(n) = sin(Wc *((n -1)-alpha)) /(((n -1)-alpha)*%pi); 
end 
end 
// Blackman Window 
for n = 1:M 
W(n) = 0.42-(0.5*cos((2*%pi*(n-1))/(M-1)))+(0.08*cos((4*%pi*(n-1))/(M-1))); 
end 
//Windowing filter coefficients 
h = hd.*W; 
disp(h,'Filter Coefficients are') 
[hzm,fr]= frmag (h,256) ; 
subplot(2 ,1 ,1) 
plot(2*fr, hzm) 
xlabel( ' Normalized Digital Frequency w'); 
ylabel( 'Magnitude '); 
title( ' Frequency Response of FIR LPF using Blackman Window ') 
hzm_dB = 20* log10 (hzm); 
subplot (2 ,1 ,2); 
plot(2*fr , hzm_dB); 
xlabel( ' Normalized Digital Frequency W' ); 
ylabel( 'Magnitude in dB'); 
title('Frequency Response of FIR LPF using Blackman Window'); 
~~~

# CALCULATION:
<img width="803" height="1280" alt="image" src="https://github.com/user-attachments/assets/2f528916-a009-4814-abab-298b7d00b37c" />

# OUTPUT: 

<img width="491" height="457" alt="image" src="https://github.com/user-attachments/assets/88caf2bf-00e2-4081-8caa-9434c05c341c" />
<img width="759" height="719" alt="image" src="https://github.com/user-attachments/assets/4dec761d-27bd-479c-abf4-941a3bc221d9" />

# RESULT: 

Thus design of low pass FIR digital filter using-Blackman-Window waveforms were plotted and output was verified.

# AIM 2: To perform DESIGN OF HIGH PASS FIR DIGITAL FILTERS using SCILAB.

# APPARATUS REQUIRED: 
PC installed with SCILAB. 

# PROGRAM: 
~~~
clc ; 
close ; 
M=input('Enter the Odd Filter Length ='); 
Wc=input('Enter the Digital Cut off frequency ='); 
alpha= (M -1)/2 // Center Value 
for n = 1:M 
if (n ==alpha+1) 
hd(n) = 1-Wc/ %pi ; 
else 
hd(n) = -sin(Wc *((n -1)-alpha)) /(((n -1)-alpha)*%pi); 
end 
end 
// Blackman Window 
for n = 1:M 
W(n) = 0.42-(0.5*cos((2*%pi*(n-1))/(M-1)))+(0.08*cos((4*%pi*(n-1))/(M-1))); 
end
//Windowing filter coefficients 
h = hd.*W; 
disp(h,'Filter Coefficients are') 
[hzm,fr]= frmag (h,256) ; 
subplot(2 ,1 ,1) 
plot(2*fr, hzm) 
xlabel( ' Normalized Digital Frequency w'); 
ylabel( 'Magnitude '); 
title( ' Frequency Response of FIR HPF using Blackman Window ') 
hzm_dB = 20* log10 (hzm); 
subplot (2 ,1 ,2); 
plot(2*fr , hzm_dB); 
xlabel( ' Normalized Digital Frequency W' ); 
ylabel( 'Magnitude in dB'); 
title('Frequency Response of FIR HPF using Blackman Window');
~~~

# CALCULATION:
<img width="864" height="1280" alt="image" src="https://github.com/user-attachments/assets/142f0036-bc3b-4d16-9fea-2af6b9277fe8" />

# OUTPUT: 
<img width="451" height="479" alt="image" src="https://github.com/user-attachments/assets/412e9b24-c178-4407-8e51-42a0e2576fc0" />
<img width="756" height="718" alt="image" src="https://github.com/user-attachments/assets/f5b9e1a7-b83f-4731-abbd-e44530a220a0" />


# RESULT: 
Thus design of HIGH pass FIR digital filter using-Blackman-Window waveforms were plotted and output was verified.

# AIM 3: To perform DESIGN OF BAND PASS FIR DIGITAL FILTERS using SCILAB.

# APPARATUS REQUIRED: 
PC installed with SCILAB. 

# PROGRAM:
~~~
clc ; 
close ; 
M=input('Enter the Odd Filter Length ='); 
Wc=input('Enter the Digital Cut off frequency ='); 
Wc2=Wc(2); 
Wc1=Wc(1); 
alpha= (M -1)/2 // Center Value 
for n = 1:M 
if (n ==alpha+1) 
hd(n) =(Wc2-Wc1)/%pi ; 
else 
hd(n) =((sin(Wc2 *((n -1)-alpha)))-(sin(Wc1 *((n -1)-alpha))))/(((n -1)-alpha)*%pi); 
end 
end 
// Blackman Window 
for n = 1:M 
W(n) = 0.42-(0.5*cos((2*%pi*(n-1))/(M-1)))+(0.08*cos((4*%pi*(n-1))/(M-1))); 
end 
//Windowing filter coefficients 
h = hd.*W; 
disp(h,'Filter Coefficients are') 
[hzm,fr]= frmag (h,256) ; 
subplot(2 ,1 ,1) 
plot(2*fr, hzm) 
xlabel( ' Normalized Digital Frequency w'); 
ylabel( 'Magnitude '); 
title( ' Frequency Response of FIR BPF using Blackman Window ') 
hzm_dB = 20* log10 (hzm); 
subplot (2 ,1 ,2); 
plot(2*fr , hzm_dB);  
xlabel( ' Normalized Digital Frequency W' ); 
ylabel( 'Magnitude in dB'); 
title('Frequency Response of FIR BPF using Blackman Window'); 
~~~

# CALCULATION:
<img width="1600" height="1341" alt="image" src="https://github.com/user-attachments/assets/8426e92f-8568-457c-9456-5ab631fa611a" />

# OUTPUT: 
<img width="556" height="458" alt="image" src="https://github.com/user-attachments/assets/5c7dead8-fc28-4c1d-8560-c32ecfd1f355" />
<img width="771" height="715" alt="image" src="https://github.com/user-attachments/assets/19600c28-673f-4b64-b32f-a74784e6aafd" />


# RESULT: 
Thus design of BAND pass FIR digital filter using-Blackman-Window waveforms were plotted and output was verified.

# AIM 4: To perform DESIGN OF BAND STOP FIR DIGITAL FILTER using SCILAB.

# APPARATUS REQUIRED: 
PC installed with SCILAB. 

# PROGRAM: 
~~~
clc ; 
close ; 
M=input('Enter the Odd Filter Length ='); 
Wc=input('Enter the Digital Cut off frequency ='); 
Wc2=Wc(2); 
Wc1=Wc(1); 
alpha= (M -1)/2 // Center Value 
for n = 1:M 
if (n ==alpha+1) 
hd(n) =1-((Wc2-Wc1)/%pi); 
else 
hd(n) =((sin(Wc1 *((n -1)-alpha)))-(sin(Wc2 *((n -1)-alpha))))/(((n -1)-alpha)*%pi); 
end 
end 
// Blackman Window 
for n = 1:M 
W(n) = 0.42-(0.5*cos((2*%pi*(n-1))/(M-1)))-(0.08*cos((4*%pi*(n-1))/(M-1))); 
end 
//Windowing filter coefficients 
h = hd.*W; 
disp(h,'Filter Coefficients are') 
[hzm,fr]= frmag (h,256) ; 
subplot(2 ,1 ,1) 
plot(2*fr, hzm) 
xlabel( ' Normalized Digital Frequency w'); 
ylabel( 'Magnitude '); 
title( ' Frequency Response of FIR BSF using Blackman Window ') 
hzm_dB = 20* log10 (hzm); 
subplot (2 ,1 ,2); 
plot(2*fr , hzm_dB); 
xlabel( ' Normalized Digital Frequency W' ); 
ylabel( 'Magnitude in dB'); 
title('Frequency Response of FIR BSF using Blackman Window');
~~~

# CALCULATION:
<img width="1600" height="1268" alt="image" src="https://github.com/user-attachments/assets/b6bff03b-aeac-47e0-a61c-53a969717d1d" />

# OUTPUT: 

<img width="582" height="512" alt="image" src="https://github.com/user-attachments/assets/858521be-7f0d-4ad7-981b-a5a7b152f727" />

<img width="759" height="723" alt="image" src="https://github.com/user-attachments/assets/b4d75779-e19f-4855-a639-dc15ebc7f7cf" />


# RESULT: 
Thus design of BAND STOP FIR digital filter using-Blackman-Window waveforms were plotted and output was verified.
