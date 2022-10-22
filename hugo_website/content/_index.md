---
title: kuramoto cicada
---

# kuramoto cicada

![screenshot](screenshot.png)


This is a Max/MSP package containing two externals: **cicada~** and **cicada_chorus_control**.

Copyright &copy; 2022 Daniel Brown  
Contact: daniel@intelligentmusicsystems.com

#### Installation

Download the _kuramoto-cicada_ folder from [here](). Copy the (entire) folder to your Max Packages folder (it's probably somewhere like _Documents/Max [version number]/Packages)_.

#### About

The **cicada~** object came from a study on simulating the sound of cicadas chirping, as part of a larger interest I have in computationally modelling natural sounds--the stochastic rhythms of nature.

The original paper about it is [here, ](https://xenakis2022.uoa.gr/proceedings/) in the Proceedings of the 2022 Xenakis Centenary International Symposium (pp. 394-406), along with a bunch of other really interesting papers on stochastic music and Xenakis.

Cicadas emit "chirps" by [expanding and retracting their abdomens](https://en.wikipedia.org/wiki/Cicada#Song), which buckles and unbuckles a hard structure on each side of them, producing a loud noise. The most interesting aspect of a cicada's chirping is that, in the presence of other cicadas, it will often very quickly synchronize its chirps with the others'. Large groups of cicadas will chirp in near-perfect synchrony, a behavior called "chorusing."

The **cicada~** object models this behavior by implementing the [Kuramoto model](https://en.wikipedia.org/wiki/Kuramoto_model) for systems of coupled oscillators, which has been suggested for how cicadas and other insects acheive this chorusing behavior in the absence of a central "conductor."

The **cicada~** object is essentially an LFO with two types of modifications: 

First, it has several stochastic attributes which cicada chirps (and other natural sounds) display, and which you can control in order to layer different degrees of randomness onto your waveforms: amplitude, "chirp" length (i.e. period), length of time chirping, length of time not chirping, and the influence of neighbor chirps on whether a cicada will start or stop chirping. By modifying these variables, you can get a lot of different flavors of constantly changing sonic textures.

Second, you can connect **cicada~** objects to one another with patch cords, and then change what's called the _Kuramoto coefficient_ attribute, which governs how likely the cicadas are to synchronize:
+ at value 1, connected cicadas will chirp in synchrony;
+ at value 0, connected cicadas will ignore each other according to their individual feelings;
+ at value -1, connected cicadas will try to alternate their chirps with each other.

Between these values, you can make really interesting polyphonic and heterophonic behavior emerge.

Originally the **cicada~** object was used with a Max subpatch that sent constant filtered white noise into it (based on an example from the excellent book [_Designing Sound_](https://books.google.com/books/about/Designing_Sound.html?id=YGymQwAACAAJ) by Andy Farnell), which the object then amplitude-modulated. You can see this in the cicada~.maxhelp file. But you can send any signal you want through the object and thus use it like an LFO. You can also trigger events with it. 

{{< youtube at3zoSr--_k >}}


Logo attribute: [Cicada icons created by Icongeek26 - Flaticon](https://www.flaticon.com/free-icons/cicada)