
EXPERIMENT 3
CIRCUIT 1

AIM: Design and analyze the MOS differential amplifier circuit for the following specifications.
Vdd=2.5V,P<=3mW,Vicm=1.3V,Vocm=1.4V,Vp=0.5V. Perform DC analysis,transient analysis,and frequency response and extract the required parameters.
CIRCUIT DIAGRAM: ![image](https://github.com/user-attachments/assets/6517842a-a382-4a34-89b1-340af4a62dae)

THEORY:
Amplifiers are a basic part of analog circuit design, and MOSFETs serve as excellent amplification devices. Among the various amplifier configurations, the common-source (CS) amplifier is widely used. It is characterized by having the gate as the input, the drain as the output, and the source as the common terminal for AC signals.
CS Amplifier with a Resistor Load
CS Amplifier with a Current Source Load
CS Amplifier with a Resistor Load
In this configuration, a resistor acts as the load at the drain terminal.
Large-Signal Operation
The behavior of the circuit changes as the input voltage (VIN) varies:
When VIN is near zero, the MOSFET remains off, and the output voltage (VOUT) is at VDD.
As VIN approaches the threshold voltage (VTH), the MOSFET starts conducting, leading to a small voltage drop across the load resistor (RL), causing VOUT to decrease.
When VIN exceeds VTH, the MOSFET enters saturation, and the amplifier operates effectively.
As VIN continues to increase, the MOSFET eventually enters the linear region, causing a further drop in VOUT.
Since MOSFETs function best as amplifiers in saturation, the effective operating range of the amplifier is limited to values where the transistor remains in saturation.
PROCEDURE:
1. Open LTspice, Launch LTspice on your computer.
2. Create a New Schematic
 Click on File → New Schematic to open a new schematic window.
3. Place Components
Power Supply (V1)
     *Press F2 (Component selector).
    * Search for voltage and place it in the schematic.
     *Right-click on it and set DC Value = 2.5V.
    *Connect it to the top node of the circuit.
Resistors (R1, R2, R3)
   *Place three resistors:
   * R1 and R2 = 1.833kΩ (connected from V1 to the drain of each MOSFET).
   *R3 = 0.4166kΩ (connected from the MOSFET source node to ground).
    *Right-click each resistor to edit values.
MOSFETs (M1, M2)
    #Press F2, search for NMOS, and place two NMOS transistors.
   # Ensure that the drains are connected to R1 and R2, respectively.
    #Connect the sources of both MOSFETs together and to R3.
    #Ensure the gates are connected to V2 and V3.
Input DC Sources (V2, V3)
    $Press F2, select voltage, and place two DC voltage sources.
     Set both sources to 1.3V (Right-click → Set DC value to 1.3V).
    Connect V2 to the gate of M1 and V3 to the gate of M2.
4. Connect Ground
    Press G to place a ground.
    Connect ground to V2, V3, and the bottom node of R3.
5. Simulation Settings
   Click on Simulate → Edit Simulation Cmd.
    Go to DC Op Pnt (Operating Point Analysis).
    Click OK and place the .op statement in the schematic.
6. Running the Simulation
    Click the Run button (green play icon).
    The DC operating points (voltages and currents) will be displayed.
7. Observing Results
    Click on different nodes (wires) in the schematic to display voltage values.
    Click on MOSFETs to see their operating currents.
CALCULATIONS:
Length (L = 0.5u)
Width (W = 50u)
RD = 1.833kΩ
Gain = 14.6dB
1. Differential Pair Operation
    M1 and M2 (NMOS transistors) form a differential amplifier with a common-source connection.
    The gates of M1 and M2 receive the same input voltage (1.3V), ensuring balanced operation.
    The common-source node (bottom connection of M1 and M2) is connected to a current source (R3), setting the total bias current.
2. Current Mirror Load
    R1 and R2 (1.833kΩ each) act as load resistors, converting drain currents into output voltages.
    Because both inputs (V2 and V3) are equal (1.3V), the circuit is symmetric, meaning M1 and M2 share equal current.
3. Bias Current Analysis
    The resistor R3 (0.4166kΩ) determines the total tail current, which splits equally between M1 and M2 under ideal conditions.
    The total tail current ItailItail​ is given by:
    Itail=VSSR3
    Itail​=R3​VSS​​ Given V_SS = 2.5V,
    Itail=2.5V0.4166kΩ≈6mA
    Itail​=0.4166kΩ2.5V​≈6mA Thus, each transistor ideally conducts:
    ID=Itail2=3mA
    ID​=2Itail​​=3mA
4. Output Voltage Behavior
    The drain voltages at M1 and M2 are determined by the current flowing through R1 and R2:
    Vout=VDD−(ID×RD)
    Vout​=VDD​−(ID​×RD​) Given I_D = 3mA and R1 = 1.833kΩ:
    Vout=2.5V−(3mA×1.833kΩ)=2.5V−5.5V
    Vout​=2.5V−(3mA×1.833kΩ)=2.5V−5.5V This indicates MOSFETs may not be in saturation, and adjustments to resistance values or supply voltage may be needed.
5. Circuit Applications
    This differential pair is used in amplifiers, comparators, and ADCs.
    It provides high gain and common-mode rejection.
    The circuit can be modified for differential gain analysis by applying a small differential input (V2 ≠ V3).

RESULTS:
DC Operating Point
![image](https://github.com/user-attachments/assets/44c12d60-8ebf-413d-b54a-25304b4c0c4d)

AC analysis
![image](https://github.com/user-attachments/assets/862ac7d1-c281-4369-8d8e-f3575459952e)

Transient analysis
![image](https://github.com/user-attachments/assets/ca51fc52-fc44-49b1-88a0-be3db8e79af8)




INFERENCE:
*The circuit functions correctly as a differential pair.
*Current division is as expected based on circuit symmetry.
*For amplification, an AC input could be applied, and further frequency analysis could be performed.

CIRCUIT 2
CIRCUIT DIAGRAM:
![image](https://github.com/user-attachments/assets/56bf69a7-58ec-4d43-8611-8922be45800c)


RESULT:
1. DC Operating Point Analysis (.op)
This will provide bias voltages and currents for all nodes and components.Expect MOSFETs to be in saturation if designed correctly.
The drain voltages should be symmetric if the circuit is balanced.
![image](https://github.com/user-attachments/assets/d4f33bfa-428d-4b8b-b37d-66f492072d59)


2. Transient Analysis (.tran 5m)
This shows the time-domain response to sinusoidal inputs.Expect differential amplification:
If  increases,  should decrease accordingly.The output waveform will depend on the differential gain.
![image](https://github.com/user-attachments/assets/2374ca9f-f735-4b49-a3b5-d11af25f4363)


3. AC Analysis (.ac dec 10 100 100G)
This gives the frequency response of the circuit.
Important observations:Gain at low frequencies (mid-band gain).Bandwidth (cutoff frequency) beyond which gain drops.Common-mode rejection (ideally high).
![image](https://github.com/user-attachments/assets/105510f7-e1f0-4edd-8f39-fac039050448)


INFERENCE:
*The circuit amplifies the difference between  and , rejecting common-mode signals.
*The gain depends on the MOSFET parameters and resistor values.
*The bandwidth tells how fast the amplifier can respond to input changes.
*If designed properly, it functions as a high-gain, differential-input amplifier, useful in analog signal processing.

CIRCUIT 3

CIRCUIT DIAGRAM:
![circuit](https://github.com/user-attachments/assets/f3ca81e7-3848-4c1d-b71a-06c7a19c361b)

RESULT:
This circuit appears to be a differential pair using NMOS transistors with a current source. The key aspects of this circuit:
Power Supply: 2.5V (V1).
Differential Input Signals: Two sine wave signals (V2 and V3) with 1.3V DC offset, 50mV amplitude, and 1kHz frequency.
Load Resistors: R1 and R2 (1.833K each). Current Source: NMOS M3 with a bias voltage of 0.86V (V4).
Output Nodes: Drains of M1 and M2.

Expected Simulation Results:
The circuit operates as a differential amplifier, meaning the output voltage will be the difference between the drain voltages of M1 and M2.Since V2 and V3 are complementary sinusoidal signals (AC 1 and AC -1), the output voltage will also be a sinusoidal signal reflecting their difference.The gain of the differential pair depends on the transconductance of the MOSFETs and the load resistance.The current source (M3) provides a stable tail current, ensuring proper differential operation

    DC Analysis – To determine biasing conditions.
    AC Small Signal Analysis – To find gain and frequency response.
    Transient Analysis – To observe time-domain behavior.
    Common-Mode Analysis – To determine common-mode rejection.
    Differential Mode Analysis – To understand the amplification of the difference signal.

1. DC Analysis (Biasing Conditions)
This helps determine the operating points (DC voltages and currents).
MOSFET Operation:
        M1M1​ and M2M2​ form a differential pair.
        M3M3​ acts as a current source, ensuring a constant tail current.
Current Source (M3):
        Gate voltage = 0.86V (V4).
        This sets the drain current of M3, which is split between M1 and M2.
Expected Results:The tail current ItailItail​ through M3 is determined by its transconductance and threshold voltage.The drain voltages of M1 and M2 will settle around some DC value based on the balance of currents.
![dc op](https://github.com/user-attachments/assets/6cd41a82-f6b0-423f-9f57-4d2f4f121ef7)

2. AC Small Signal Analysis
To find voltage gain and frequency response.
Differential Gain:
    Ad=VoutVin=gmRD
    Ad​=Vin​Vout​​=gm​RD​
where gmgm​ is the transconductance of M1, M2, and RDRD​ is the drain resistance (R1 or R2).
 Common-Mode Gain:
        Measures how much the circuit amplifies common-mode signals.
        Ideally, it should be low for good Common-Mode Rejection Ratio (CMRR).
   ![ac](https://github.com/user-attachments/assets/1b7439ae-156a-4090-9d41-24a603d69d44)


3.Frequency Response:
        Cutoff frequency depends on parasitic capacitances.
        Gain bandwidth is influenced by CgdCgd​, CgsCgs​, and load resistance.
Expected Results:The circuit should provide high differential gain.The common-mode gain should be minimal.Bandwidth can be estimated from the pole locations.
![fa](https://github.com/user-attachments/assets/21123a74-2f04-4c7d-a80b-2c966eab2c81)

4. Transient Analysis
To observe the circuit’s time-domain behavior.
Input Signals:
        V2=1.3V+50mVsin⁡(2π1000t)V2​=1.3V+50mVsin(2π1000t)
        V3=1.3V−50mVsin⁡(2π1000t)V3​=1.3V−50mVsin(2π1000t)
 Expected Output: Output voltage will be a sinusoidal waveform proportional to the difference between V2 and V3.The phase inversion occurs at the drains of M1 and M2.
![transient 2](https://github.com/user-attachments/assets/1964c52d-a390-437c-a76a-357a943d0055)

CALCULATIONS:
Power Supply: 2.5V (V1).
Differential Input Signals: Two sine wave signals (V2 and V3) with 1.3V DC offset, 50mV amplitude, and 1kHz frequency.
Load Resistors: R1 and R2 (1.833K each).
Current Source: NMOS M3 with a bias voltage of 0.86V (V4).
Output Nodes: Drains of M1 and M2.

INFERENCE:
*Amplification: The circuit functions as a differential amplifier, with gain dependent on transconductance and resistance.
*Common-Mode Rejection: It should suppress common-mode signals effectively.
*Dynamic Response: The transient analysis will confirm the signal amplification.
*Frequency Dependence: The gain may roll off at high frequencies due to capacitances.
