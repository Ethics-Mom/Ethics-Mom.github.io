---
layout: post
title: Human Metabolism
date: 2026-11-08
---

# Human Metabolism
Human metabolism is comprised of many complex chemical processes, here we will be only looking at the energy balance

## The basic model
The "first law" of this energy balance model is:  
$$ c_{1}\frac{d W}{dx}=E_{in}-E_{out} $$  
Where c_1 is the constant value 7716.179176 calories per kg (calorie density of adipose tissue), W is body mass in kg, E_in is one's energy intake in calories (i.e. the diet), and E_out is the energy leaving your body in calories (i.e. metabolism).
For clarification the calories being used are American calories, British kilo-calories, or the general nutritional calorie.  

## Interpreting of real world data
I have tried many methods for this. If you are recording your daily diet and weight then calculating your metabolism by rewriting the above equation is easy to calculate off of today's and yesterday's weight however this produces an unusably noisy metabolism output.
For my current method I utilize [Savitsky-Golay](http://constans.pbworks.com/w/file/fetch/121217343/SavitskyGolay.pdf) filters rather than Epanechnikov filters.
Where Epanechnikov kernel best works for data that is a heap of results not ordered in time (i.e. scores in a game), a Savitsky-Golay kernel best works for time series data (i.e. diet each day)
Skipping over many of the other methods i have tried the following procedure.  
Step 1, Smooth out the diet: I used a 15 point smoothing kernel (Table I in the link above, make sure to divide the result by the NORM row, in this case by 1105) to smooth out the diet.  
In Excel I used the kernel centered on the current day to prevent biases during gradual increases or decreases. The following code is for a cell in row 9 acting on diet data in column C.  
~~~
=SUMPRODUCT(C2:C16, {-78;-13;42;87;122;147;162;167;162;147;122;87;42;-13;-78})/1105
~~~
Step 2, Get derivative of body mass: I used a 15 point 1st derivative quadratic kernel (Table III).
the following code is for a cell in row 9 acting on weight data in column B
~~~
=SUMPRODUCT(B2:B16, {-7;-6;-5;-4;-3;-2;-1;0;1;2;3;4;5;6;7})/280
~~~  
Step 3, Take the previous two results and feed them into our "first law" to calculate for metabolism  
$$ E_{out}=E_{in}-7716.179176*\frac{d W}{dx} $$  

## An Unexpected Result
I processed over two years of data, during both stable and unstable dietary conditions. and strangely there's an oscillation that appears in the metabolism.
Even when i try different methods of data analysis it is still there.
It seems to be roughly ±500 calories and has a period of 12-24 days.  
I have gone looking for papers regarding this infradian rhythm in the metabolism but i couldn't find anything for humans.  

## An Additional Result
This took a while since I did it by hand, but i took the metabolism with its oscillations and tried to remove them by sampling the extremas and recording a point at their midpoint.
I then tried running it through a PID control model with the PV as the simulated metabolism, and SP as the real diet data (averaged over the previous extrema range).
I used the real (midpoint) metabolism data to calibrate the model which yielded the following control gains.  

| Control Gain | Value |
|---|---|
| Kp | 0.031092925 |
| Ki  | -0.000044045 |
| Kd | -0.05938515 |  

With this model I was able to get a coefficient of correlation of 0.67 between the simulated and real data.
