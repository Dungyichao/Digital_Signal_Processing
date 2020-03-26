# Digital Signal Processing on Embedded System

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

## 2.1 Sampling and Quantization
When a signal input to a system, if we want to know what the signal we get, then we need to do sampling. It will be great if we can get infinite sample, however, that is imposible and waste of resources. According to <b>Nyquist Theorem</b>, the sampling frequency should be two times larger than the maximum frequency of the input signal in order to reconstruct the exact signal. 
f_s >= 2*f_max 
where f_s is sampling frequency and f_max is the maximum frequency of the input signal.




