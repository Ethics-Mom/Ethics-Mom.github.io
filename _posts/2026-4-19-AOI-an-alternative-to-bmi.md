# AOI, a BMI alternative based in dimensional analysis
I have recently grown more disappointed in BMI. And it's not just because medical professionals have been moving away from using it, there is something inherently busted about the system.\
So, I took it upon myself to try and find a fix to it, and the system I have come up with is the Aspect Oblateness Index, or AOI.
In this post I will use metric units (m and kg) but at the end I will include the equation in Imperial units as well.

for reference BMI is calculated as follows:\
$$ \text{BMI}=\frac{M}{H^{2}} $$\
With M as your weight in kg and H as your height in m

## Motivation
At the core of dimensional analysis are things called dimensionless quantities, basically they are values that don’t have an associated unit.
Some examples are Aspect ratio which is distance / distance, Mach number which is speed / speed, and specific weight which is density / density.
In all cases all the units cancel each other out and you're left with a unitless number. 
The cool thing about them is they tend to describe a system in a very characteristic way. 
For example, a plane wing which is moving through the air with a certain Reynolds number and Mach number behaves identically to a scaled down model as long as the Reynolds number and Mach number are the same.
This makes those wind tunnel tests with a smaller version of said vehicle work.\
By using a dimensionless quantity we can assure that height does not effect our results and that stature is measured correclty!
(Looking at you BMI)\
For our needs aspect ratio is the clear winner.
Simply measuring the aspect ratio of someone's body would be difficult and with people being shaped differently from each other this proves to be a very rough path.
Instead, I opt to continue using height and weight and calculate aspect ratio from there.
This now poses a different question; how do we calculate the aspect ratio from height and weight alone?
We could calculate the volume, but without knowing what shape it's in we're no closer to solving this.
I chose to model a person as a spheroid with axes a,b,b.

![spheroid diagram with axes](https://github.com/Ethics-Mom/Ethics-Mom.github.io/blob/main/Assets/Spheroid.png?raw=true)

I did this because a person tends to gain weight in their middles, and less so on their head and feet.
So now the problem is solving for the aspect ratio of a spheroid (hence the name aspect oblateness index)

## AOI derivation
In the following equation H will stand for height in meters, W will stand for weight in kg, and aspect ratio will be given as R.
The axes a and b are equal to 
$$ a=\frac{H}{2} $$\
$$ b=\frac{\text{Width}}{2} $$\
The aspect ratio is\
$$ R=\frac{b}{a} $$\
The Volume of the spheroid is given by:\
$$ V=\frac{4}{3}\pi ab^{2} $$\
We can get rid of b via substitution and multiply by density \
$$ \rho=985\frac{kg}{m^{3}} $$\
$$ M=\frac{4}{3}\pi\rho a^{3}R^{2} $$\
We may also replace a with H/2\
$$ M=\frac{1}{6}\pi\rho H^{3}R^{2} $$\
We can finally solve for the aspect ratio from height and weight\
$$ R=\sqrt{\frac{6}{\pi\rho}}*\sqrt{\frac{W}{H^{3}}} $$\
$$ R=0.0440334358089\sqrt{\frac{W}{H^{3}}} $$

## AOI 
For convenience sake I take AOI to be equal to R * 100 so that it may be read as a percentage.\
$$ AOI=4.40334358089\sqrt{\frac{W}{H^{3}}} $$\
eg. if you calculate R to be 0.15, AOI will be 15 and can be read as you are 15% as wide as you are tall.

## Discussion
### Shouldnt It be Aspect Prolateness Index?
Yeah yeah its a tall sphere so its prolate and not oblate but I'm not the grammar police! and API is already a coding thing so oblate it is!

### Wait, that there in the Sqrt, that's Corpulence Index!
It sure is! Corpulence Index (CI) is like BMI but you divide mass by the cube of the height rather than the square of the height.
This does lend a bit more credance to using CI over BMI because of the whole being effected by height thing. 
AOI as a square root of CI does have particular advantages that I will explore in further posts.
### I calculated my AOI what does it mean?

| AOI Range | Category |
|---|---|
| 14- | Underweight |
| 15-16 | Healthy/Lean |
| 17-18 | Overweight |
| 19-20 | Obesity Class 1 |
| 21-22 | Obesity Class 2 |
| 23+ | Obesity Class 3 |

### Imperial Units
$$ AOI=732.597578731\sqrt{\frac{W}{H^{3}}} $$\
for lb and in.
