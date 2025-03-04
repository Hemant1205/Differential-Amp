### **"Differential Amplifier"**

A differential amplifier is a fundamental building block in analog circuit design, widely used in applications such as signal amplification, noise reduction, and data acquisition systems. It amplifies the difference between two input signals while rejecting common-mode noise, making it ideal for high-precision circuits, including operational amplifiers and analog front-end systems.

In modern electronics, differential amplifiers play a crucial role in communication systems, biomedical instrumentation, and sensor interfaces, where signal integrity is critical. The ability to suppress external interference and unwanted signals makes them superior to single-ended amplifiers in noisy environments.

### **question:Vdd=2.2v , p<=2.2mv , Vicm=1.2v, Vocm=1.25v , Vp=0.4v**

**Circuit 1** <br>
![1](https://github.com/user-attachments/assets/587b725b-aeb4-41f9-ae69-5b2a77ddc0ba)


**Step 1:Dc analysis design Rd and Rss**
![2](https://github.com/user-attachments/assets/0b7cb906-652b-4640-9544-a512792683eb)


from the calculation we have finded Iss value as 1mA <br>
Id1 and Id2 as 0.5mA <br>
Rd as 1.9kohm <br>
Rss as 400ohm <br>
Vgs=vg - vp = 1.2v - 0.4v = 0.8v <br>
Vov = vgs - vth = 0.8v - 0.366v = 0.434v <br>

### **DC Analysis**

To set the operating point go to Configure Analysis and select Dc operating Point <br>

to set correct operating point vary width and length values 
width = 6.45u <br>
length = 180n <br>
![3 5](https://github.com/user-attachments/assets/39af177a-32ff-4a57-a108-f8f290a62638)


### **Analysis**

**Increase Vicm from 1.2v to 1.3v and observe Vocm and Vp** <br>
| **Common-Mode Input Voltage (V_ICM)** | **Output Voltage (V_out)** | **Voltage at Point P (V_P)** |
|--------------------------------------|--------------------------|--------------------------|
| **1.2V**                            | **1.24836V**             | **0.4V**                |
| **1.3V**                            | **1.1V**                 | **0.46V**               |

### Effect of VICM on Vout and VP

As the common-mode input voltage \( VICM \) increases, the source voltage \( VP \) also increases, causing a shift in the operating point. This leads to a higher drain current, resulting in a greater voltage drop across \( RD \), which reduces \( Vout \).

![4](https://github.com/user-attachments/assets/42c202ef-0e9b-4483-9d50-c0009ef3431d)

### **Calculate maximum input and output Swing & GAIN**

![5](https://github.com/user-attachments/assets/426f1d2a-9617-43e5-996c-7953c50c8c51)


### **TRANSIENT ANALYSIS**
go to configure Analysis and select transient analysis then <br>
stop time as 5m <br>
time to start saving data as 0 <br>

• Waveform Type: Sine Wave
• Amplitude: 50 mV
• DC Offset: 1.2 V
• Frequency: 1 kHz


![6](https://github.com/user-attachments/assets/172d04f3-90aa-4c44-8481-e4e21d14ac24)


### **AC Analysis**

go to configure analysis and select AC Analysis
• Type of sweep: Decade
• Number of points per decade: 5
• Start frequency: 0.1 Hz
• Stop frequency: 1 THz

Set <br>
AC Amplitude as 1 and AC Phase as 0 in V1 <br>
AC Amplitude as 1 and AC Phase as 180 in V2 <br>

  ![Screenshot 2025-02-17 184334](https://github.com/user-attachments/assets/b5b9b5b2-cc27-459c-87d9-27411895f901)
 

   ![7](https://github.com/user-attachments/assets/fb617ea0-bcf4-4935-8f59-160b4a80681a)


### **Circuit 2** <br>

Replacing Resistor with Current Source

![8](https://github.com/user-attachments/assets/efefb14d-0951-49fe-9ce7-3f8d7230fc73)


### **DC Analysis**

![9](https://github.com/user-attachments/assets/afa53a7b-a162-4f70-9fc1-7d187a3b65fe)

### **TRANSIENT ANALYSIS**
![10](https://github.com/user-attachments/assets/dccdf0df-f54a-4c19-bf95-de8c9911e144)

 Vocm = 1.36 -1.13
  Vin = 1.25 - 1.15 V

  Gain = vocm / Vin
   = (1.36 - 1.13) / (1.25 - 1.15)

 = 2.3
 Gain in dB: 20 log (2.3)
 =7.23
 



### **AC Analysis**
<img width="959" alt="11" src="https://github.com/user-attachments/assets/cefc6773-aa3d-44f4-b8ba-d0bf731b317a" />




### **Circuit 3** <br>

Replacing current Source with MOSFET 

![image](https://github.com/user-attachments/assets/6d27b01b-f1ff-4995-8ab1-ff0f91a954a4)


How to find Vb?
Vb = vth + Vp <br>
Vb = 0.366v + 0.4v <br>
Vb = 0.766v <br>

### **DC Analysis**

<img width="282" alt="12" src="https://github.com/user-attachments/assets/56f78ce5-4a87-4dbf-bd1d-667fb2c26719" />

 # Transient analysis:
 give ac amplitude as 1 for one mosfet and 0 gor other mosfet 

![13](https://github.com/user-attachments/assets/cceb0642-bc40-47f3-80b1-76afeb2417eb)

# AC analysis:
<img width="959" alt="14" src="https://github.com/user-attachments/assets/7a170258-3c04-43df-a547-8e14f0a4447f" />



# DC sweep :
<img width="959" alt="image" src="https://github.com/user-attachments/assets/15f102e5-5ba4-40c5-965c-3c6d8668217b" />


# Result:

1. Circuit-1: 
   - The DC analysis shows that the MOSFETs operate in saturation with balanced drain currents when input voltages are equal.  
   - The transient response confirms proper differential behavior.  
   - The AC analysis indicates moderate gain and common-mode rejection.  

2. Circuit-2:  
   - Replacing the resistor with a current source improves bias stability, as seen in the DC analysis.  
   - The transient response is more stable, ensuring better symmetry.  
   - The AC analysis shows increased gain and bandwidth compared to Circuit-1.  

3. Circuit-3:  
   - The DC analysis confirms that the MOSFET-based current source regulates the tail current effectively.  
   - The transient response maintains signal accuracy with improved performance.  
   - The AC analysis shows higher gain and bandwidth.  
   - The DC sweep analysis validates expected output variations.  

# Inference:  

This experiment explored differential amplifier configurations: resistor-based, current source-based, and NMOS-based, each affecting gain, bandwidth, and stability differently.  

- Resistor: High bandwidth, low gain, low CMRR.  
- Current source: High gain, high CMRR, slightly lower bandwidth.  
- NMOS (CMOSN): Highest gain.  

 Best Configuration Based on Need:  
1. High bandwidth → Resistor  
2. Maximum gain→ NMOS (CMOSN)  
3. Better CMRR→ Current source or NMOS (CMOSN)



















































 
