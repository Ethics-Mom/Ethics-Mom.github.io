## AOI, a BMI alternative based in dimensional analysis
I've been dissapointed with BMI, and mainly its failings with short and tall people.
In general many physicians are moving away from relying on it so heavily for a myriad of reasons.
However I figured it would be nice to take a stab at it, The following will be in metric (m, kg) though I will give American units at the end.

### BMI
BMI is calculated as follows:
$$ \text{BMI}=\frac{M}{H^{2}} $$
With M as your weight in kg and H as your height in m
### AOI
the basis for AOI will be in the body's aspect ratio.
I decided to go with aspect ratio because it was a dimensionless quantity that i thought well described someone's stature.
The aspect ratio being someones width divided by someones height.
With different body types simply measuring a width would be innacurate and time conuming, so we are better off finding a way to calculate width via a person's height and weight.
In order to do this I assumed the body to be a spheroid with axes a,b,b where
$$ a=\frac{H}{2} $$
$$ b=\frac{\text{Width}}{2} $$
and aspect ratio R is
$$ r=\frac{b}{a} $$
