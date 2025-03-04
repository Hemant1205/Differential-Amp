### **"Differential Amplifier"**

A differential amplifier is a fundamental building block in analog circuit design, widely used in applications such as signal amplification, noise reduction, and data acquisition systems. It amplifies the difference between two input signals while rejecting common-mode noise, making it ideal for high-precision circuits, including operational amplifiers and analog front-end systems.

In modern electronics, differential amplifiers play a crucial role in communication systems, biomedical instrumentation, and sensor interfaces, where signal integrity is critical. The ability to suppress external interference and unwanted signals makes them superior to single-ended amplifiers in noisy environments.

### **question:Vdd=2.2v , p<=2.2mv , Vicm=1.2v, Vocm=1.25v , Vp=0.4v**

**Circuit 1** <br>

![exp3c](https://github.com/user-attachments/assets/cc3bf852-bada-4373-87e6-2b139cfb7672)


**Step 1:Dc analysis design Rd and Rss**
![WhatsApp Image 2025-03-03 at 11 46 51_889aaf8d](https://github.com/user-attachments/assets/14b7637c-256c-46c2-9336-72dc8e6a7ded)


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
![exp3dc](https://github.com/user-attachments/assets/4fd87afb-13ef-4c3a-bb74-81046cc8b822)


### **Analysis**

**Increase Vicm from 1.2v to 1.3v and observe Vocm and Vp** <br>
| **Common-Mode Input Voltage (V_ICM)** | **Output Voltage (V_out)** | **Voltage at Point P (V_P)** |
|--------------------------------------|--------------------------|--------------------------|
| **1.2V**                            | **1.24836V**             | **0.4V**                |
| **1.3V**                            | **1.1V**                 | **0.46V**               |

### Effect of VICM on Vout and VP

As the common-mode input voltage \( VICM \) increases, the source voltage \( VP \) also increases, causing a shift in the operating point. This leads to a higher drain current, resulting in a greater voltage drop across \( RD \), which reduces \( Vout \).

![Screenshot 2025-03-02 165923](https://github.com/user-attachments/assets/9935d54d-cf30-47ea-80d7-b6691c1cbb31)

### **Calculate maximum input and output Swing**

![WhatsApp Image 2025-03-03 at 11 57 11_d4811d07](https://github.com/user-attachments/assets/fbadbee5-9795-4b4d-a718-e68649dce37e)


### **GAIN**
![WhatsApp Image 2025-03-03 at 11 57 32_f7c5bba7](https://github.com/user-attachments/assets/c0bf6b33-33eb-4e2d-b80c-e3134eb34557)



### **TRANSIENT ANALYSIS**
go to configure Analysis and select transient analysis then <br>
stop time as 5m <br>
time to start saving data as 0 <br>

• Waveform Type: Sine Wave
• Amplitude: 50 mV
• DC Offset: 1.2 V
• Frequency: 1 kHz


![Screenshot 2025-03-02 222413](https://github.com/user-attachments/assets/87c3521e-0a76-4b97-a9cf-b4032c82922d)


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
 

   ![1 4](https://github.com/user-attachments/assets/e38ceac5-13a9-46b8-ad3c-efeac570178f)


### **Circuit 2** <br>

Replacing Resistor with Current Source

![image](https://github.com/user-attachments/assets/0da961ce-df7a-4896-acaa-8f31f65f5bab)


### **DC Analysis**

![Screenshot 2025-03-02 222935](https://github.com/user-attachments/assets/d922b434-5aa1-4bb5-8855-bf281f8d0f53)

### **TRANSIENT ANALYSIS**
![image](https://github.com/user-attachments/assets/7c668786-784e-48bd-93b2-21d45c488f80)
 Vocm = 1.36 -1.13
  Vin = 1.25 - 1.15 V

  Gain = vocm / Vin
   = (1.36 - 1.13) / (1.25 - 1.15)

 = 2.3
 Gain in dB: 20 log (2.3)
 =7.23
 



### **AC Analysis**
<img width="959" alt="image" src="https://github.com/user-attachments/assets/75f328de-9ee0-4011-ab77-b6078fc720c0" />




### **Circuit 3** <br>

Replacing current Source with MOSFET 

![image](https://github.com/user-attachments/assets/6d27b01b-f1ff-4995-8ab1-ff0f91a954a4)


How to find Vb?
Vb = vth + Vp <br>
Vb = 0.366v + 0.4v <br>
Vb = 0.766v <br>

### **DC Analysis**

<img width="472" alt="image" src="https://github.com/user-attachments/assets/417842be-d7ad-4955-8086-b77ea97d490e" />

 # Transient analysis:
 give ac amplitude as 1 for one mosfet and 0 gor other mosfet 

 ![Screenshot 2025-03-02 123127](https://github.com/user-attachments/assets/431d7132-e2fb-4870-b625-a5334a2e9a9d)

# AC analysis:
<img width="959" alt="image" src="https://github.com/user-attachments/assets/56a10839-f8b8-40e4-8c2f-a01d9dda29f3" />



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



















































 
