---
title: Reference
weight: 35
---

This information is all in the **cicada~** Max help and Max reference files included with the package:

#### MESSAGES  
_int_  
Left inlet: 0 turns off, anything else turns on.

_signal_  
Left inlet: The signal that the cicada's "chirp" will modulate the amplitude of.

#### OUTLETS
+ **0** (Leftmost) (signal):  
If there is an input signal, this will output the amplitude-modulated signal.  
If no input signal and _chirp_on_signal_ is zero, this will output the amplitude envelope.
If no input signal and _chirp_on_signal_ is non-zero, this will not output.
+ **1** (bang):  
Bangs when amplitude envelope is zero.
+ **2** (float):    
The peak value of amplitude envelope, when this value is hit.
+ **3** (list):  
Connect this outlet to the right inlet of another cicada to make that cicada "listen" and synchronize (if the _coupling_strength_ attribute is high) to this one.

#### ATTRIBUTES
+ **_chirp_on_start_** (long) (settable/not gettable)    
Non-zero: start chirping when object is turned on.  
Zero: stochastically decide to chirp according to _chirping_time_mean_ and _nonchirping_time_mean_ attribute values when object is turned on.  
Default is non-zero.
​
+ **_chirping_** (long) (settable/not gettable)  
Manually start or stop chirping.  
zero: silences cicada.  
non-zero: starts cicada chirping.  
Default is non-zero (on).  

+ **_chirp_on_signal_** (long) (settable/not gettable)  
Output based on presence of input signal.  
zero: send output without input signal.  
Non-zero: send output only when a signal is coming in inlet.  
Default is zero.  

+ **_amplitude_randomness_** (float) (settable/not gettable)  
Range: 0 to 1  
At 0 all chirps will have peak value 1.0. Increase to randomize peak values. Follows a normal (Gaussian) distribution. Default is zero.  

+ **_chirp_length_mean_** (float) (settable/not gettable)  
In milliseconds.  
Follows a normal (Gaussian) distribution.  
Default is 300 ms.  

+ **_chirp_length_randomness_** (float) (settable/not gettable)  
Range: 0 to 1  
At 0 all chirps will have length equal to _chirp_length_mean_. Increase to randomize chirp lengths.  
Follows a normal (Gaussian) distribution.  
Default is zero.

+ **_chirping_time_mean_** (float) (settable/not gettable)  
In seconds  
The average amount of time in seconds the cicada will chirp without stopping.  
Follows a geometric distribution.  
Default is one second.  

+ **_nonchirping_time_mean_** (float) (settable/not gettable)  
In seconds  
The average amount of time of unbroken silence between periods of chirping.  
Follows a geometric distribution.  
Default is zero seconds.  

+ **_start_chirping_nbr_sensitivity_** (float) (settable/not gettable)  
The likelihood of starting chirping based on how many neighbors are chirping. 
If a cicada is connected to other cicadas via its left inlet and currently not chirping, higher values of this will increase its likelihood to start chirping if the other cicadas are chirping.  
Default is zero.

+ **_stop_chirping_nbr_sensitivity_** (float) (settable/not gettable)  
Likelihood of stopping chirping based on how many neighbors are chirping.  
If a cicada is connected to other cicadas via its left inlet and currently not chirping, higher values of this will increase its likelihood to stop chirping if the other cicadas are chirping.  
Default is zero.  

+ **_coupling_strength_** (float) (settable/not gettable)  
Range: -1 to 1.  
Default is zero.  
The Kuramoto coefficient. If a cicada is connected to one or more other cicadas, the following values will produce this behavior:  
  + **1**: will synchronize chirps with the other cicada(s);
  + **0**: will not synchronize at all with the other cicada(s)
  + **-1**: will alternate its chirps with the other cicada(s). With more than two coupled cicadas, this will be complicated.    
  
  At other values between these three main values, combinations of synchrony and randomness will occur.

	