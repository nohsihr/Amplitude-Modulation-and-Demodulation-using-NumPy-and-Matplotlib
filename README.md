# Amplitude-Modulation-and-Demodulation-using-NumPy-and-Matplotlib
## AIM

To implement and analyze amplitude modulation (AM) using Python's NumPy and Matplotlib libraries. Apparatus Required
Software: Python with NumPy and Matplotlib libraries

## HARDWARE
Personal Computer

## THEORY

Amplitude Modulation (AM) is a technique used in electronic communication, primarily for transmitting information via a radio carrier wave. In AM, the amplitude of the carrier wave is varied in proportion to that of the message signal. The general form of an AM signal is:<img width="290" height="152" alt="image" src="https://github.com/user-attachments/assets/dbe771a4-4857-47ca-a3e3-c9e0559add09" />


## ALGORITHM

1.	Initialize Parameters: Set the values for carrier frequency, message frequency, and sampling frequency.
2.	Generate Time Axis: Create a time vector for the signal duration.
3.	Generate Message Signal: Define the message signal as a cosine wave.
4.	Generate Carrier Signal: Define the carrier signal as a cosine wave.
5.	Modulate Signal: Apply the AM formula to obtain the modulated signal.
6.	Plot the Signals: Use Matplotlib to plot the message signal, carrier signal, and modulated signal.

## PROGRAM
    import numpy as np
    import matplotlib.pyplot as plt
    from scipy.signal import hilbert
    
    
    Ac = 17.6
    Am = 8.8
    fc = 8630
    fm = 863
    fs = 863000
    t = np.arange(0, 2/fm, 1/fs)
    
    
    m = Am * np.cos(2 * np.pi * fm * t)    
    c = Ac * np.cos(2 * np.pi * fc * t) 
    s = (Ac + m) * np.cos(2 * np.pi * fc * t) 
    
    
    env = np.abs(hilbert(s))  
    m_demod = env - np.mean(env)  
    
    
    plt.figure(figsize=(10,8))
    
    plt.subplot(4,1,1)
    plt.plot(t, m)
    plt.title('Message Signal')
    plt.xlabel('Time (s)')
    plt.ylabel('Amplitude')
    
    plt.subplot(4,1,2)
    plt.plot(t, c)
    plt.title('Carrier Signal')
    plt.xlabel('Time (s)')
    plt.ylabel('Amplitude')
    
    plt.subplot(4,1,3)
    plt.plot(t, s)
    plt.title('AM Modulated Signal')
    plt.xlabel('Time (s)')
    plt.ylabel('Amplitude')
    
    plt.subplot(4,1,4)
    plt.plot(t, m_demod)
    plt.title('Demodulated Signal')
    plt.xlabel('Time (s)')
    plt.ylabel('Amplitude')
    
    plt.tight_layout()
    plt.show()

## TABULATION
<img width="513" height="385" alt="image" src="https://github.com/user-attachments/assets/0b67986f-acfb-4e11-950a-bd9269e4cc47" />

## CALCULATION 
<img width="530" height="117" alt="image" src="https://github.com/user-attachments/assets/02185507-96ee-4b76-82ae-04fc153e4452" />

## OUTPUT
<img width="484" height="387" alt="image" src="https://github.com/user-attachments/assets/78320ca2-81a0-4647-94b5-e494c732602c" />

## RESULT
The message signal, carrier signal, and amplitude modulated (AM) signal will be displayed in separate plots. Thus AM is implemented using numPy and Matplotlib.  
