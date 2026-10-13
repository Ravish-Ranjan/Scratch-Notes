# Signal Formulas

### Digital to Digital

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

Signal Rate : no. of signals per time period

$$
S = \frac{c * N}{r}
$$

```
S : baud rate (signals/sec)
N : bitrate (bits/sec)
c : avg. no of signal per data element relative to max
r : no. of data element represented by one signal element
```

$$
N_{max} = B * r * (1/c)
$$

Line coding schemes

1. Unipolar : NRZ
2. Polar : NRZ, RZ, manchester, differencial manchester
3. Bipolar : AMI,psuedoternary
4. Multilevel : 2B/1Q, 8B/6T, 4D-PAM5
5. Multitransition : MLT-3

1. Unipolar
  1. NRZ : 1 (some volatage V), 0 (0 voltage)     normalized power = 1/2 V^2
2. Polar
  1. NRZ-Level : 1 (V1 voltage ) 0 (V2 voltage)
  2. NRZ-I : 1 (signal changes level at beginning of interval), 0 (signal remains same)     1 : go from low to high or high to low     0 : remain on the same level
  3. RZ : 1 (+V for first hald of interval then 0)  0 (-V for first half of the interval then 0)
  4. manchester : 1 (low to high transission in middle) 0 (high to low transission in middle)
  5. differencial manchester : 1 (no transission change ) 0 (transission change)
3. Bipolar
  1. AMI : 0 (0 volts) 1 (V volts but in different direction than previous 1 signal)
  2. psuedoternary : 1 (0 volts) 0 (V volts but in different direction than previous 1 signal)
4. Multilevel
  1. 2B1Q : 2-bit signal requires 2^2 levels each encodes different value eg. (00 : 3V, 01 :1V, 10 : -1V, 11 : -3V )
  2. 8B6T : 8 bits of data in 6 signal elemets using 3 voltage levels (+V,0,-V) since 8 bits value can range from 0-255 and 3 voltage levels 6 time can create 3^6 = 729 different values
  3. 4D-PAM5 : used in gitgabit ethernet 1000base-T (4D -> 4 wires pairs)(PAM -> pulse amplitude modulation) (5 -> voltage levels) 5^4 = 625 levels 
5. Multitransission
  1. MLT-3 : (3 -> voltage levels +v,0,-v) 1 (transission to next level) 0(remain at same level) sequence = (0 -> +v -> 0 -> -v -> 0)

![](asset://localhost/%2Fhome%2Fravish%2FDocuments%2FScratch%20Notes%2Fassets%2FScreenshot%20from%202026-10-13%2017-57-30.png)

Scrambling methods 

1. B8ZS (bipolar with 8-zeros substitution) : used with bipolar AMI (used cause long sequence of 0's can cause asyncronization)
  1. replace every consecutive 8 zeros with 
    1. if last 1 was +V : 0 0 0 + - 0 - +
    2. if last 1 was -V  : 0 0 0 - + 0 + -
2. HDB3 (high-density bipolar 3-zeros) : for any consecutive 4 zeros , find the no. of 1's befor it
  1. if no. of 1's is odd : replace with ( 0 0 0 V )
  2. if no. of 1's is even : replace with ( B 0 0 V )
  3. B : pulse opposite of last pulse's direction
  4. V : pulse same of last pulse's direction

### Analog to digital

pulse code modulation steps

1. sample
  1. ideal sampling (only at that time instance)
  2. natual sampling (sample but data flows with signal) 
  3. flat-top sampling (data stays as it got sampled)
2. quantize
3. encode

 