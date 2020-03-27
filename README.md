# Digital Signal Processing on Embedded System
A great website for reference: 
[https://www.dspguide.com/ch1.htm](https://www.dspguide.com/ch1.htm)


# 1. What do we need
### Software
1. codeblock: 
[https://filehippo.com/download_codeblocks/](https://filehippo.com/download_codeblocks/)
2. gnuplot:
[https://sourceforge.net/projects/gnuplot/files/gnuplot/](https://sourceforge.net/projects/gnuplot/files/gnuplot/)
<p align="center">
<img src="/img/gnuplot_start.JPG" height="80%" width="80%"> 
</p>  

# 2. Basic Knowledge
All the following summary are reference from the website: https://filehippo.com/download_codeblocks/

<p align="center">
<img src="/img/DSP_Process.JPG" height="80%" width="80%"> 
</p>  

## 2.1 ADC and DAC
### 2.1.1 Quantization
The sample-and-hold (S/H) is required to keep the voltage entering the ADC constant while the conversion is taking place. It is allowed to change only at periodic intervals, at which time it is made identical to the instantaneous value of the input signal. Changes in the input signal that occur between these sampling times are completely ignored. That is, sampling converts the independent variable (time in this example) from continuous to discrete. <br />
Quantization converts the dependent variable (voltage in this example) from continuous to discrete. Any one sample in the digitized signal can have a maximum error of ±? LSB (Least Significant Bit)

### 2.1.2 Sampling Theorem
When a signal input to a system, if we want to know what the signal we get, then we need to do sampling. It will be great if we can get infinite sample, however, that is imposible and waste of resources. According to <b>Nyquist Theorem</b>, the sampling frequency should be two times larger than the maximum frequency of the input signal in order to reconstruct the exact signal (ie. frequencies above one-half the sampling rate are lost) <br />
f_s >= 2*f_max  <br />
where f_s is sampling frequency and f_max is the maximum frequency of the input signal.

### 2.1.3 Digital-to-Analog Conversion (DAC)
Nearly all DACs operate by holding the last value until another sample is received. This is called a <b>zeroth-order hold</b>, the DAC equivalent of the sample-and-hold used during ADC. (A first-order hold is straight lines between the points, a second-order hold uses parabolas, etc.). The zeroth-order hold produces the staircase appearance. However, in the frequency domain, the zeroth-order hold results in high frequency amplitude reduction and will have the shape like sin(πx)/(πx) (called sinc function)

### 2.1.4 Analog Filters
Three types of analog filters are commonly used: <b>Chebyshev, Butterworth, and Bessel</b>. The complexity of each filter can be adjusted by selecting the number of <b>poles</b>. The more poles in a filter (by cascading the building block showing below), the more electronics it requires, and the better it performs. The following is a common building block for analog filter design, the <b>modified Sallen-Key circuit</b>.

<p align="center">
<img src="/img/Modified-Sallen-Key.JPG" height="100%" width="100%"> 
</p>

The performance comparision is in the following

<p align="center">
<img src="/img/analog-filter-compare.JPG" height="100%" width="100%"> 
</p>

The particular op amp use isn't critical, as long as the unity gain frequency is more than 30 to 100 times higher than the filter's cutoff frequency. This is an easy requirement as long as the filter's cutoff frequency is below about 100 kHz.

However, integrated circuit is difficult to make resistors directly in silicon, so <b>switched capacitor filter</b> come to the rescue. Notice that, in most systems, the frequency band between about 0.4 and 0.5 of the sampling frequency is an unusable wasteland of filter roll-off and aliased signals.   




