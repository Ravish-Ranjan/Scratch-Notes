# Signal Formulas

Nyquist formula for bitrate (noiseless)

$$
R_{max} = 2B log_2 L
$$

```
R_max : maximum bitrate for ideal noiceles low-pass channel
B : bandwidth
L : levels of bits in digital signal
```

Shannon formula for bitrate (noisy)

$$
Capacity = Blog_2{(1 + SNR)}
$$

 

$$
Capacity = Blog_2(1 + 10^{\frac{SNR_{dB}}{10}})
$$

```
Capacity : maximum bitrate
B : bandwidth
SNR : signal to noise ratio
```

power loss attenuation

$$
Signal Loss (dB) = 10log_{10}\frac{P_2}{P_1}
$$

```
P2 : power currently (Watts)
P1 : power previously (Watts)
```

why is decibals ? cause it is additive over a series of changes

Distorsion : change in the phase of signal due to different time of arrival

Noise

1. Thermal noise
2. induced noise
3. cross talk
4. impulse noise

Signal to noise ratio

$$
SNR = \frac{Signal Power}{Noise Power}
$$

$$
SNR_{dB} = 10Log_{10} SNR
$$

Latency : how much time it takes from first bit transmissted to entier signal reaching estination

$$
Latency = TransmissionTime + PropogrationTime + QueueingTime + ProcessingDelay
$$

Throughput : actually how much data can be transfered over timeperiod

```
maximum bitrate can be find from shannon or nyquist formula but there is a limit on how much data on avg can be transfered let it be ( x frames/ time period )
```

$$
Throughput = \text{Avg bits transfered over time}
$$

$$
ActualBitrate < MaximumBitrate
$$

 