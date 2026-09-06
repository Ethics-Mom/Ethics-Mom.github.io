---
layout: post
title: Application of Tolman-Oppenheimer-Volkoff Equations in Determination of Terrestrial Exoplanet Composition
date: 2026-7-12
---

# Application of Tolman-Oppenheimer-Volkoff Equations in Determination of Terrestrial Exoplanet Composition



## Abstract
The composition of terrestrial exoplanets remains the subject of great interest and research. 
It plays a large part in connecting our geophysical models of earth with the astrophysical models of the galaxy and nebulas.
In the best case only the mass and radius may be known, and using density we can arrive to an approximate and inaccurate estimation of the planet's composition.
Larger planets exhibit reletivistic effects, and the effect of compression are often ignored.
This model applies the Tolman-Oppenheimer-Volkoff equations and bulk modulus to accurately determine the possible compositions of terrestrial exoplanets.
It was expected that the metallicity of the parent star would positively correlate with a planet's iron content.
By limiting the model to silicate and iron, and assessing 112 exoplanets from NASA's Exoplanet Archive [1], 
the iron composition was found to increase 38% per 1 increase in parent star metallicity.

## Model
Three materials were chosen for use in this model: iron (core material), silicate (mantle material), and water.
This was chosen so that a Ternary diagram, 
a triangular diagram that lets you plot a three-part composition that add up to 100%
(e.g. soil with its three parts: sand, silt, and clay), could be used to visualize what compositions are being looked at.

### Initialization 

The model takes the desired mass and radius as input, then creates a series of arrays for each physical property with customizable length:
radius, mass, state, density, pressure.
The radius array is a linear interpolation from 1m to the desired radius and does not change.
The density array is initialized at a constant average calculated off of the desired mass and radius.
The Pressure array is initialized at a linear interpolation from 4E+11 Pa to 0.

### State
State stores the physical information of each material type.
It has the following values in units kg/m^3 and pa^-1:  
0: Liquid water density: 1000  
1: Liquid water compressability: 4.8E-10  
2: Ice i density: 930  
3: Ice i compressability: 1E-10  
4: Ice vi density: 1310  
5: Ice vi compressability: 7.1E-11  
6: Ice vii density: 1650  
7: Ice vii compressability: 5E-11  
8: Liquid Si density: 4375.6  
9: Liquid Si compressability: 1.73638E-12  
10: Solid Si density: 2753.6  
11: Solid Si compressability: 2.02119E-11  
12: Liquid Fe density: 8425.7  
13: Liquid Fe compressability: 1.35545E-12  
14: Solid Fe density: 10035  
15: Solid Fe compressability:  7.12037E-13

These values were calibrated to Earth [2], Europa and Callisto [3].

### Main Loop
The code first chooses a composition, then it loops through calculating the mass shell, the state, the density, and the pressure.  
$$ \frac{d m}{dr}=4\pi r^{2}\rho(r) $$  
$$ \rho=\rho_{0}(1+P\beta) $$  
$$ \frac{dP}{dr}=\frac{Gm\rho}{r^{2}}(1+\frac{P}{\rho c^{2}})(1+\frac{4\pi r^{3}P}{mc^{2}})(1-\frac{2Gm}{rc^{2}})^{-1} $$  
The differential equations are solved via euler's method.
The state is determined off of the mass fraction that has been accumulated, with iron on the bottom and water on top.
The state of those materials is then determined by pressure using the following cutoffs:  
Solid iron to liquid iron and solid silicate to liquid silicate (the crust boundary): 3E+10 Pa.  
Solid iron to liquid iron and solid silicate to liquid silicate (the core boundary): 3.3E11 Pa.  
Water to ice i: 6E7 Pa.  
Ice i to ice vi: 1.1E9 Pa.  
Ice vi to ice vii: 2.2E9 Pa.  
This is looped 10 times, by then it is highly stable and a mass shell can be summed to get the total planetary mass.
This mass is then compared to the input mass and an error is calculated, plotted on the chart, then the code selects a new composition.
This continues for all compositions to a specified resolution.

## Results

### The Solar System
Values were taken from NASA's Planetary fact sheets [4].  
Internal state charts plotted for composition with the lowest error with 0% water, Because of this only the inner planets are plotted.  
**Mercury**  
![Mercury composition Ternary Diagram](https://github.com/Ethics-Mom/Ethics-Mom.github.io/blob/main/Assets/Mercury%20Composition.png?raw=true)
![Mercury internal values](https://github.com/Ethics-Mom/Ethics-Mom.github.io/blob/main/Assets/Mercury%2068f32s00w%20Internals.png?raw=true)
Plotted values: 68% Fe, 32% Si  
**Venus**  
![Venus composition Ternary Diagram](https://github.com/Ethics-Mom/Ethics-Mom.github.io/blob/main/Assets/Venus%20Composition.png?raw=true)
![Venus internal values](https://github.com/Ethics-Mom/Ethics-Mom.github.io/blob/main/Assets/Venus%2032f68s00w%20Internals.png?raw=true)
Plotted values: 32% Fe, 68% Si  
**Earth**  
![Earth composition Ternary Diagram](https://github.com/Ethics-Mom/Ethics-Mom.github.io/blob/main/Assets/Earth%20Composition.png?raw=true)
![Earth internal values](https://github.com/Ethics-Mom/Ethics-Mom.github.io/blob/main/Assets/Earth%2032f68s00w%20Internals.png?raw=true)
Plotted values: 32% Fe, 68& Si  
**Mars**  
![Mars composition Ternary Diagram](https://github.com/Ethics-Mom/Ethics-Mom.github.io/blob/main/Assets/Mars%20Composition.png?raw=true)
![Mars internal values](https://github.com/Ethics-Mom/Ethics-Mom.github.io/blob/main/Assets/Mars%2022f78s00w%20Internals.png?raw=true)
Plotted values: 22% Fe, 32% Si  

### Exoplanets

From the NASA Exoplanet Archive planets were selected that met the folloring criteria:  
• Known mass  
• Known radius  
• Known parent star metallicity  
• Mass under 10 Earth masses
This narrowed it down to 286 canditates.
The code was then ran for each planet, water was assumed to be 0% for the sake of analysis.
Each plannet was assesed on this 0% water boundary and was discarded if the minimum mass error was too high.
This further narrowed it down to 112 exoplanets who both abided to the afformentioned criteria as well as yeilding usable results from the code.
Many of the planets removed in that final step were likely comprised in large part by water.
The iron composition percentage was then compared to the parent star's metallicity.

![The linear regression in question](https://github.com/Ethics-Mom/Ethics-Mom.github.io/blob/main/Assets/ResultsGraph.png?raw=true)

Linear regression reveals that iron composition increases 38% per 1 increase in parent star metallicity.
Binning the stars every 0.1 metallicity and taking the average, in a historgram-like way reveals a clear trend as well.
These findings cooberate the nebular hypothesis of planetary system formation.

## Conclusions
Temperature is missing from this model as while
implementing it would mean a much greater accuracy in
matter state determination and density calculations,
modeling planetary temperature are beyond the scale of
this project. Such models need to be able to take
thermal contributions from radioactive decay in the core
as well as the star. Such a system exists in quasi-
equilibrium and is highly dependent on system age.
Water is also difficult to model, so many shortcuts and
approximations had to be made. Hopefully with the
implementation of a temperature model python
packages such as SeaFreeze may be utilized to get a
proper model of water.
Addition of a geochemical model may further help by
allowing us to use physical properties of specific
minerals rather than silicate in general.


## Aknowledgements
I would like to thank Dr. Ashley Kehoe for her sponsorphip in Embry-Riddle's 2025 Discovery Day and for getting me into scientific research.

## References

[1] California Institute of Technology (2025). NASA Exoplanet Archive.
https://exoplanetarchive.ipac.caltech.edu/  
[2] Volgyesi, Lajos & Moser, M. (1982). THE INNER STRUCTURE OF THE
EARTH. Periodica Polytechnica Chemical Engineering. 26  
[3] O.L. Kuskov, V.A. Kronrod (2005). Internal structure of Europa and Callisto,
https://doi.org/10.1016/j.icarus.2005.04.014.  
[4] NASA (2025). Planetary fact sheet.
https://nssdc.gsfc.nasa.gov/planetary/factsheet/index.html
