# AOI, a BMI alternative based in dimensional analysis
I've been dissapointed with BMI, and mainly its failings with short and tall people.
In general many physicians are moving away from relying on it so heavily for a myriad of reasons.
However I figured it would be nice to take a stab at it, The following will be in metric (m, kg) though I will give American units at the end.

## BMI
BMI is calculated as follows:\
$$ \text{BMI}=\frac{M}{H^{2}} $$\
With M as your weight in kg and H as your height in m
## AOI derivation
AOI stands for the Aspect Oblateness Index, the basis for AOI will be in the body's aspect ratio.
I decided to go with aspect ratio because it was a dimensionless quantity that i thought well described someone's stature.
The aspect ratio being someones width divided by someones height.
With different body types simply measuring a width would be innacurate and time conuming, so we are better off finding a way to calculate width via a person's height and weight.
In order to do this I assumed the body to be a spheroid with axes a,b,b where\
$$ a=\frac{H}{2} $$\
$$ b=\frac{\text{Width}}{2} $$\
and aspect ratio R is\
$$ R=\frac{b}{a} $$\
![spheroid diagram with axes](https://github.com/Ethics-Mom/Ethics-Mom.github.io/blob/main/Assets/Spheroid.png?raw=true)
The Volume of the spheroid is given by:\
$$ V=\frac{4}{3}\pi ab^{2} $$\
We can get rid of b via substitution and multiply by density \
$$ \rho=985\frac{kg}{m^{3}} $$\
$$ M=\frac{1}{6}\pi\rho H^{3}R^{2} $$\
We may also replace a with H/2\
$$ M=\frac{4}{3}\pi\rho a^{3}R^{2} $$\
We can finally solve for the aspect ratio from height and weight\
$$ R=\sqrt{\frac{6}{\pi\rho}}*\sqrt{\frac{W}{H^{3}}} $$\
$$ R=0.0440334358089\sqrt{\frac{W}{H^{3}}} $$\
## AOI 
I prefer to multiply the aspect ratio by 100 so it can be read as a percentage\
$$ AOI=4.40334358089\sqrt{\frac{W}{H^{3}}} $$\
R=0.15 would become AOI = 15 which can be interpreted as this person is 15% as wide as they are tall.\
## Discussion
### Shouldnt It be Aspect Prolateness Index?
Yeah, but API is already a coding thing so AOI it is\
### Wait, that there in the Sqrt, that's CI!
It sure is! Corpulence Index (CI) is like BMI but you divide mass by the cube of the height rather than the square of the height.
This does lend a bit more credance to using CI over BMI, but AOI as a square root of CI does have its advantages that I will explore in further posts.
### I calculated my AOI what does it mean
| AOI Range | Category |
|-------|--------|
| 14- | Underweight |
| 15-16 | Healthy/Lean |
| 17-18 | Overweight |
| 19-20 | Obesity Class 1 |
| 21-22 | Obesity Class 2 |
| 23+ | Obesity Class 3 |
### American Units
$$ AOI=732.597578731\sqrt{\frac{W}{H^{3}}} $$\
for lb and in.
