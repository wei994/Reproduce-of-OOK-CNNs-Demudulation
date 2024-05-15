# Reproduce-of-OOK-CNNs-Demudulation
The code to reproduce the OOK CNNs Demudulation


In the code, first I define a function to generate the dataset based on the SNR, range Z, and transmission power P.
Input: SNR, range Z, and transmission power P.
output: Numerical signal of bit 1 and bit 0, the standard deviation of total noise of bit 1 and bit 0, the optimal threshold

Here is the clue about the function.
1. we have the diode parameters to modulate the signal, and then simulate the channel gain. In the article, there are no pointing errors and turbulence, so the total channel gain is channel diffuse.
2. And then try to simulate the receiver, after being transmitted in water, the signal is received by SiPM and generates related current and voltage.
3. Add noise, the thermal, dark current noise, etc. can be considered as one Noise that is normally distributed, with SNR and the transmission power, we can get the noise power which is the variance of the normally distributed noise.
4. The Numerical signal  = received_signal_n + noise_n
5. And then calculate the Ins_BER and Ave_BER

For now, the function is not stable,I am trying to fix the problem.

