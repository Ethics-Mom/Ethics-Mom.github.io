---
layout: post
title: Smoothing uniformly sampled data with the discrete Epanechnikov Kernel
date: 2026-05-03
---

# Smoothing uniformly sampled data with the discrete Epanechnikov Kernel
Often when dealing with data noise is a persistant issue that we have to contend with. 
Weather it's precise scientific readings or noisy casual data I've found smoothing it to be useful.\

![An Example of Discrete Epanechnikov smoothing in action](https://github.com/Ethics-Mom/Ethics-Mom.github.io/blob/main/Assets/SmoothingExample.png)

An Example of Discrete Epanechnikov smoothing applied to real world data.

## Motivation
Now for kernel smoothing the best continuous kernel is the Epanechnikov kernel, A parabola with area 1 and bounds 
{% comment %} 
[-1,1]
{% endcomment %}
. This works great for find ing the density of one dimensional data. but for data taken at regular time intervals we need something similar but different.\
We just need a discrete kernel, like the ones used for bluring and sharpening images, that has this parabolic shape, a sum of 1 (as in normalized), and is zero at it's ends.
We need the sum to be equal to one so that when we convolve (look up convolution or np.convolve if youre a pyhead) it with our data we smooth it.
If it's more than zero it will make the values bigger, and vice-versa for less than 1.

## Derivation
This one is surprisingly simple. It's just a parabola so here's an example of a derivation.\
Let's choose a size of 4, we will square it to 16.\
The center of the kernel will be 16, 4<sup>2</sup>.\
And as we travel outward we subtract the squares.\
4<sup>2</sup>-0<sup>2</sup>/ = 16\
4<sup>2</sup>-1<sup>2</sup>/ = 15\
4<sup>2</sup>-2<sup>2</sup>/ = 12\
4<sup>2</sup>-3<sup>2</sup>/ = 7\
4<sup>2</sup>-4<sup>2</sup>/ = 0\
Omitting the ends with 0, since they wont contribute to the kernel's weighted average, this gives us the values:

| 7 | 12 | 15 | 16 | 15 | 12 | 7 |

To normalize our kenel we will divide by 84, the sum of the components.\
This can be easily calculated by [A000447](https://oeis.org/A000447)\

$$ D=\frac{4n^{3}-n}{3} $$\
Where D is the Denominator (is 84 above) and n is the size (4 for this example)
This gives us a final Kernel of appoximately:

| 0.08333 | 0.14286 | 0.17857 | 0.19048 | 0.17857 | 0.14286 | 0.08333 |

## Python Implementation
I have a custom sized smoothing kernel [here]().
a guide to using it is included in its README file.

## Excel Implementation
If you want to smooth a tall row of data with smoothing 8 in Excel use this hideous, abhorrent mess i made. Be sure to put it on cell B7.
The one upside with this monstrocity is that it automatically normalizes it, even it one end doesnt have data (you can have it run all the way to the end of your data without clipping your smoothed data)
```
=(13*(A1+A8)+24*(A2+A9)+33*(A3+A10)+40*(A4+A11)+45*(A5+A12)+48*(A6+A13)+49*A7)/(-0.00000000001247/540*COUNTBLANK(A1:A13)^4+1/3*COUNTBLANK(A1:A13)^3-6.5*COUNTBLANK(A1:A13)^2-41/6*COUNTBLANK(A1:A13)+455)
```
And yes that countblank polynomial appoximation is really accurate, like to r<sup>2</sup>=0.999\
And if you're here and reading this, Thank you.

!(Beautiful Image)[https://pbs.twimg.com/media/Gs7s4m6aIAA3Mqs?format=jpg&name=large]
