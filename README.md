# EXP-1
## Aim:
To do the DC analysis,Transient and AC analysis of a CS amplifier circuit and 
extract the various parameters associated using LT Spice.

##Components required:
MOSFETs:nmos4, Ressisters:1k, Voltage supply:(1.8V,0.9V) and connecting wires.

## Theory:
MOSFET is a device and is one of the most basic compontent and also a very important comonent/device in electronics .

The importance of MOSFET is due to its compact design, low power consumption,simple geometry and compatibilty in VLSI technology.\
There are three different configurations in which the mosfet can be connected that are drain, gate and the source. The most popular being common source and common drain configurations.

The Mosfet acts as an amplifier in the saturation region of operation where Vgs > Vth,Vgd < Vth and Vds>=Vov for an N channel mosfet.
In the common source configuration there is a 180 degree phase shift between input and output. \
_There is very high input impedance (Ig=0) ideally infinite._

The drain current:

**I<sub>d</sub> = 1/2 k<sub>n</sub> V<sub>ov</sub><sup>2</sup>** ; **V<sub>ov</sub>=V<sub>gs</sub>-V<sub>th</sub>** and **k<sub>n</sub>=u<sub>n</sub> C<sub>ox</sub> W/L**

Output is taken from the drain end.

### DC Analysis:
DC analysis is done to ensure the MOSFET operates in saturation region and to calculate the DC operationg point of the transistor. This prevents signal distortion .\
DC analysis helps in the determination of the biasing resistors.\
DC analysis helps in getting a correct operating point despite the fluctuation in the other parameters.

### Transient Analysis:
Transient Analysis is done to analyse the response of the circuit to time varying signals. 

Transient Analysis is helpful to determine the signl distorton, DC shift between the input and the output.
Transient Analysis plays key role in detecting issues like phase distortion.This is essential for high speed applications like communication systems.

### AC Analysis:
 AC Analysis is the small signal analysis of the circuit.This is done to determine the Gain of the amplifier circuit .\
 AC Analysis helps to analyze the Frequency Reponse of the amplifier circuit.
In  AC Analysis the gain is given by **A<sub>v</sub> = -g<sub>m</sub> R<sub>d</sub>**

## Procedure:
1.Create a new folder and name it as project(name) file. Save the LT spice file in this folder.

2.Name the MOSFET as CMOSN and the length as 180nm and width as 3um initially.

3.For the PMOS name it as CMOSP and set the length as 180nm and width as 3um respectively.

4.**DC Analysis:** For DC analysis set up the circuit as per the circuit diagram with proper connections ensuring valid circuit for further analysis.
Apply the DC voltage of Vdd=1.8V and Vgs = 0.9 V. Go to simulate option in the tab and edit simulation command, click on DC analysis and press ok.(.op)
Click on Run in the tab menu to get the DC operating point, Vout and Id.

5.**Transient Analysis:** For Transient analysis apply a sine wave input of Vgs=0.9V with an amplitude of 50mV and frequency of 1kHz by going to advanced menu in the voltage setting option.go to simulate option in tab ,edit simulation command, click on transient analysis and give the stop time as 3m and click ok.(.tran 3m) Now Run to visualise the response of the circuit to a time varying signal.

6.**AC Analysis:** For AC analysis go to spice directive and give the library file path for the simulator to access the data through the path. Go to simulate option in the tab, edit simulation command, click on AC analysis and mention the time of sweep as decade, no of points as 20 and frequency as. 1Hz to 1THz and click on ok. Now Run to analyze the gain and frequency response of the circuit(.ac dec 20 .1 1T).

# Circuit:
![Screenshot 2025-02-17 203917](https://github.com/user-attachments/assets/8c6db871-25f1-4069-a4d4-1286e52bab4a)

# Calculation:
Power = 50uW.

Loop Equation: V<sub>dd</sub>=V<sub>ds</sub>+I<sub>d</sub>*R<sub>d</sub>

P=I*V (I<sub>d</sub>=27.78uA , V<sub>dd</sub>=1.8V).

Length=500nm,

Widhth=480nm,

V<sub>ds</sub>=1.7V

gain=-20dB(from AC analysis).

Q point is (1.7V,27.78uA).

## Results:

1.**DC Analysis:**

![Screenshot 2025-02-17 204118](https://github.com/user-attachments/assets/c95c5c21-9757-497d-9dc8-ee631614e6e4)
Id=27.78uA\
Vout=1.77V\

DC Operating point : (1.77V,27.78uA) is obtained for 480nm Width and 500nm Length.

2.**Transient Analysis:**
![Screenshot 2025-02-17 204632](https://github.com/user-attachments/assets/4d358f3c-b4fd-497e-a654-bdc46b993b5e)
Vout=1.77V\

3.**AC Analysis:**
![Screenshot 2025-02-17 204916](https://github.com/user-attachments/assets/b67d11cd-7ecd-4f17-9ae1-9ff7505ca639)
Gain=-20dB.

## Inference:
1. The MOSFET current is directly proportional to its width, and variations in width affect the current flow. In saturation, the MOSFET functions as an amplifier, providing the desired negative gain as given by **A_v = -g_m R_D**.  

2. Q-point stability in the saturation region enables linear amplification, with increased gain in the mid-band frequency range (small signal analysis).  

3. Transient analysis reveals the circuit’s time-domain response, essential for high-speed applications, while AC analysis helps in designing circuits with the desired gain, impedance matching, and understanding frequency response.

