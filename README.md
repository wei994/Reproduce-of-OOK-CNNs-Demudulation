# Reproduce-of-OOK-CNNs-Demodulation
**The code to is reproduce the result in  OOK_CNNs_Demodulation**

**About the files**

"Reproduce_FTD__OOK_CNNs.ipynb" is to reproduce the result from the "OOK_CNNS" paper.

"Generate_CSV_dataset.ipynb" is to generate the dataset for CNN models. 

"BER_Rb.ipynb" the previous code to evaluate the effect of Rb(Bit rate) on BER.


**"Reproduce_FTD__OOK_CNNs.ipyn"**

The function"Simulated_dataset(SNR, Z, P, Watertype, Noise='Gauss')" generates the signal based on the SNR, range Z, and transmission power P.
First to define the watertype. (channel loss and turbulence)

Input: SNR, range Z, transmission power P, noise type and water type

output: Numerical signal of bit 1 and bit 0, the standard deviation of total noise of bit 1 and bit 0, the optimal threshold

1. we have the diode parameters to modulate the signal, and then simulate the channel gain. The article has no pointing errors and turbulence, so the total channel gain is channel diffuse.
2. Then try to simulate the receiver, after being transmitted in water, the signal is received by SiPM and generates current and voltage.
3. Add noise, the thermal, dark current noise, etc. can be considered as one Noise that is normally distributed, with SNR and the transmission power, we can get the noise power which is the variance of the normally distributed noise.
4. The Numerical signal  = received_signal_n + noise_n
5. And then calculate the Ins_BER and Ave_BER
Different noise types have been tested.

**"Generate_CSV_dataset.ipynb"**

This file is to generate the dataset 'supervised_dataset.csv' for supervised learning. Using the function defined in "Reproduce_FTD__OOK_CNNs.ipyn"


