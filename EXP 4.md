Linear Integrated Circuit
Current Mirroring Experiment
PART-A
Aim:Design and Analyze Current mirror circuit as active load in amplifier circuit.
Circuit Diagram:
https://1drv.ms/f/c/7ecf385e62f246e1/Euf-MiLkzjJGoqj3RFdAfz8BLXxyEzXCa3nK9Mh76T4ZSA?e=cRy5BC
Given :Vdd=1.8V.
P<=1mW.
Av>-10V/V. 
It=P/Vdd.
It=Iref+Ix.

DC Analysis:
https://1drv.ms/f/c/7ecf385e62f246e1/Euf-MiLkzjJGoqj3RFdAfz8BLXxyEzXCa3nK9Mh76T4ZSA?e=j6iKcO
For mirror ratio 1:1:
It=Iref+Ix. for mirror ratio 1:1 ratio iref is equal to Ix.
the given values are, P= 1mw. vdd=1.8v.
Dc analysis :
circit 1
we know that It=P/vdd. It = 1mw/1.8v = 0.55mA. Iref is half of the It value that is 0.275 mA. the given W/L values to get ratio 1:1 are 2.8um/180nm. we need to provide vin value such a way that the circuit should be in saturation . now the provided value is 0.854v.
output for L = 180nm
https://1drv.ms/f/c/7ecf385e62f246e1/Euf-MiLkzjJGoqj3RFdAfz8BLXxyEzXCa3nK9Mh76T4ZSA?e=9uBkNW
DC 1
for L =500nm
https://1drv.ms/f/c/7ecf385e62f246e1/Euf-MiLkzjJGoqj3RFdAfz8BLXxyEzXCa3nK9Mh76T4ZSA?e=ygcwW0
l 2
for L= 1um
https://1drv.ms/f/c/7ecf385e62f246e1/Euf-MiLkzjJGoqj3RFdAfz8BLXxyEzXCa3nK9Mh76T4ZSA?e=B3I9zX
Transient analysis:
Transient Analysis is used to simulate the time-domain response of a circuit when a time-varying input (such as a sine wave or pulse) is applied. It helps in analyzing circuit behavior over time, including signal amplification, switching characteristics, and transient response.

Transient Analysis Parameters: • Stop time: 10 ms
• Step time: 2ms • Time to start saving data: 0 s
https://1drv.ms/f/c/7ecf385e62f246e1/Euf-MiLkzjJGoqj3RFdAfz8BLXxyEzXCa3nK9Mh76T4ZSA?e=ybXuam
the obtained gain is equal to vout/vin
vout/vin = 10.15v/v

AC analysis:
Simulation Parameters: • Type of sweep: Decade
• Number of points per decade: 10 • Start frequency: 0.1 Hz
• Stop frequency: 1 THz
https://1drv.ms/f/c/7ecf385e62f246e1/Euf-MiLkzjJGoqj3RFdAfz8BLXxyEzXCa3nK9Mh76T4ZSA?e=CV9QbO
Input Signal Parameters: • Waveform Type: Sine Wave
• Amplitude: 50 mV
• DC Offset: 0.854 V
• Frequency: 1 kHz
The obtained gain is 21.4 dB and the practical value is 20dB.
3dB:
The obtained 3dB bandwidth is 316.22khz
For the ratio 1:2
Calculations:
Power <= 1mW
Vdd = 1.8V
Itotal = power/Vdd = 1mW/1.8 = 55.5mA
ID= Itotal/3 = 0.185mA.
1:2 ratio = 0.185mA : 0.37mA.
DC analysis:
1.Case 1: 180nm
circuit diagram:
https://1drv.ms/f/c/7ecf385e62f246e1/Euf-MiLkzjJGoqj3RFdAfz8BLXxyEzXCa3nK9Mh76T4ZSA?e=PNRs7s
output:
https://1drv.ms/f/c/7ecf385e62f246e1/Euf-MiLkzjJGoqj3RFdAfz8BLXxyEzXCa3nK9Mh76T4ZSA?e=Ml7dPr
Vout= 1.20094V Vx= 1.20934V Itotal = 0.185mA
PMOSFET 1 = length is 180nm, width is 70um
PMOSFET 2 = width is 140nm
NMOSFET = length is 180nm, width is 135.867um

case 2:
L= 500nm
output:
https://1drv.ms/f/c/7ecf385e62f246e1/Euf-MiLkzjJGoqj3RFdAfz8BLXxyEzXCa3nK9Mh76T4ZSA?e=28iHIU
case 3:
L =1um
output:
https://1drv.ms/f/c/7ecf385e62f246e1/Euf-MiLkzjJGoqj3RFdAfz8BLXxyEzXCa3nK9Mh76T4ZSA?e=QRQsh6
transient analysis:
Replace DC input with an AC signal. Use SINE(dc_offset, Amplitude, Frequency). Go to "Simulate" > "Edit Simulation Cmd" > "Transient". Set Stop Time: 10ms. Run the simulation. Our dc_offset = 0.854V and assume amplitude as 50mV and frequency as 1Khz.
https://1drv.ms/f/c/7ecf385e62f246e1/Euf-MiLkzjJGoqj3RFdAfz8BLXxyEzXCa3nK9Mh76T4ZSA?e=RgGPiN
 The obtained gain is 11.68v/v
 The obtained gain is 11.68v/v
AC analysis:
https://1drv.ms/i/c/7ecf385e62f246e1/EQnK6dLbzdBMloaXARfjMFEBjq8d6J_Y7H4olJwiquQhmQ?e=bdXeTx

3dB bandwidth:
https://1drv.ms/i/c/7ecf385e62f246e1/EbcfkaAGkF1NuTpPbLJn6CYBg16e6VyBlJMLhceDCjLIeQ?e=OlpYxw

inference:
1)Transient analysis of the amplifier with the 1:1 current mirror configuration (L=180nm) yielded a voltage gain (Av) of 10.15 V/V , which is slightly above the design Av > 10.

2)The experiment confirms that channel length modulation significantly impacts current mirror accuracy 3)the current ix slightly increases whwn we did 1:2 ratio.

PART -B:
circuit diagram with aim:
https://1drv.ms/f/c/7ecf385e62f246e1/Euf-MiLkzjJGoqj3RFdAfz8BLXxyEzXCa3nK9Mh76T4ZSA?e=bkHfZT
circuit:
https://1drv.ms/f/c/7ecf385e62f246e1/Euf-MiLkzjJGoqj3RFdAfz8BLXxyEzXCa3nK9Mh76T4ZSA?e=x0hCwK

dc analysis:
![image](https://github.com/user-attachments/assets/036dd429-3196-4f02-b0a3-9f7c848360e0)

 as per the parameters of the differential amplifier Vdd = 2.5V, Id(M1 and M2)=0.608mA, Vout = 1.38V and as per the circuit question current mirror ratio of M3 amd M4 1:2.
we need to give Iref =0.608mA keeping L=180nm constant for all the mosfet for perfect current mirroring, by trial and error width was found to be W(4) = 3.5um, W(3) = 3.5um. W3 is double the W4 because we need to double increase the Id(M3).

Transient analysis:
![image](https://github.com/user-attachments/assets/709acdbc-c0e4-4e60-b0ef-25dd28329b3f)

AC analysis:
![image](https://github.com/user-attachments/assets/854325f4-551d-4669-9661-9f573775ac58)


conclusion :Current mirrors play a crucial role in biasing circuits, especially in differential amplifiers, ensuring stable operation with minimal variation. By implementing NMOS current mirrors as bias voltage generators, differential amplifiers achieve better gain, stability, and power efficiency, making them a key component in modern analog IC design.
