---
layout: post
title: A Metaphysical model of Psychology
date: 2026-06-20
---

# A (Meta)physical Basis for a Model of Psychology

Recently I've been getting more into Mathematicism, Platonism, and Hegalianism and have taken up the view that indeed "all is number".
More precisely I beleive that the universe is ultimately mathematical, and that via emergance the human mind exists similarly to a fractal's surface.
Something made deterministically, from nondeterministic roots in quantum mechanics, creating a non-deterministic mind. 
In that fractal-like state I think the human mind has its own freedom, not just as part of the universe and it's driving forces, 
but as a system in which the chaotic noises play a qualitative effect on psychological decisions. 
And in a world where math applies everywhere, within projections, and even withing phase spaces, we should try an to analyze the mind within our projective and illusory experience of it.

## Inspirations

In trying to model the mind I first looked to the psychological drives, and Freud's and Jung's theories.
I started with Eros and Thanatos and interated from there, merging and splitting drives as I saw fit.
In general my rule was a **Drive** is not a **Capability** (i.e. Intelligence, Perception, or Memory) and was not a **State** (i.e Emotion, Energy, Sanity)
a drive is just a driving force. I decided to keep the concepts of **Posession** (when one drive completely takes over the mind) and
**Overdetermination** (where an mental state is driven by multiple drives, deeply reenforcing it). Eventually I settled upon 5 drives:  

### Thanatos (The Survival Drive)
This is the drive that pulls you to act, delights from witnessing destruction, and emotionally detatches you to do what you need to do to survive (kill animals or other people)
Though this drive really isnt useful anymore, so it remains deeply shunned in the mind of most people, usually only emerging as strange, violent dreams or emerging fully in sport hunters, muderers, soldiers, etc.
In possession it blackens the mind and makes the body move on its own.

### Eros (The Bodily Drive)
This is the bodily urges and desires, Hunger, Boredom, Libido.
Its important to listen to it a little, but obviously too much is unhealthy.
Negatively, it may also maniftest feelings of anger.
In possession it manifests in a hedonistic haze of abesnt minded indulgence.

### Mania (The Hubris Drive)
This is the drive the ego sends out to defend itself, manifesting in narcissism, power seeking, and power tripping.
While it can drive you to stand up for yourself, it's expression often shows deeper insecurity.
In negative expression it gives feelings of rage, frustration, and abashed, in positive expression it gives feelings of mania and power.
In possession it can manifest as a hard-headed and illogical competitiveness.

### Techne (The Diligent Drive)
This one drives your desire to create, work, make things, organize things, solve problems, and learn about things.
It feels satisfied over a job well done, or a display of immense skill.
Techne may also drive principals alongside Mania (both as a "im too good for these things" and as setting an internal order)
In negative expression it can create feelings of anxiety or antsyness, in positive expression it gives feelings of satisfaction.
Techne posession often manifests as the flow state.

### Psyche (The Soul Drive)
The Psyche Drive drives introspection, actualization, sociality, and connection.
This one's the most complex, but I couldnt bring myself to split it as the feelings produced by the euphoria of self discovery and of oneness with someone else is quite similar.
Though I can see the argument to split Psyche on inwards vs outwards lines.
Psyche in negative expression gives lonely, lost, or disphoric feelings, and in positive expression often gives feelings of agape or platonic love, euphoria, and fulfilment.

## Setting a Basis

Inspired off of the physics of particles I decided to take the drives to be analagous to forces, moving the mental state. 
And for the mental state I decided that modeling it like a velocity made a lot more sense. For one, the force is equivalent to a change in velocity, 
and when such forces are removed the velocity remains constant, unlike position which drifts without a force, and with a restoring force more often oscillates than not.
Additionally, the mental state only exists over time, when time is frozen it cannot be seen and the mind seems to not exsit (which fits in line with Anima as a moving thing).
So I will denote the mental state as a vector:  
$$ \overrightarrow{S} $$  
There are multiple drives acting upon this state, so we can represent the net drive resulting from j drives and a set of as a vector:  
$$ \overrightarrow{D}=\sum_{j}^{}\overrightarrow{D_{j}}\omega_{j} $$  
This is a weighted sum, with weights as omega_j.
Using these two we can take newton's second law,  
$$ \overrightarrow{F}=m\frac{d \overrightarrow{v}}{dx} $$  
though it becomes clear we should probably have some inertia-like term, and I beleive that is the place of the aforementioned capabilities, 
which will be represented with c as the intertia in changes between two specific states. We can then create our own "second law":  
$$ \frac{d\overrightarrow{S} }{dt}=\overrightarrow{D}c $$  
which we can further turn into a discrete morphism-like state change.  
$$ \overrightarrow{S_{1}}-\overrightarrow{S_{0}}=\Delta t\overrightarrow{D}c_{0\rightarrow 1} $$  
This equation is quite useful for analyzing changes in the brain's state, for example:
### Ex: Perception
Starting at State 0 (some undefined rest state) and moving to State 1 (the noticing state) the primary driver of this change is environmental.
Only a miniscule driving force needs to occur in order to notice something, and this change happens over a very short period of time, and the state change is also minor.
Expressed mathematically, the capability of going from a state of not noticing to a state of noticing is:  
$$ c_{0\rightarrow 1}=\frac{\overrightarrow{S_{1}}-\overrightarrow{S_{0}}}{\Delta t\overrightarrow{D}} $$  
A small numerator against two minuscule denominators would logically make the capability very high, which follows intuition that that capability would be high.
We can also deduce from the math that states that are closer or futher away from a state of noticing (a state of actively observing, vs spacing out) would take more time or more force to make the state change.  

## A Larger Structure.
While this serves as a solid basis to understand the way the brain's state changes, the larger structure of the mind is uncertain, it's difficult to logically rule out many differet models, but we can list some possibilities.  
### Big Net
The mind could be a big net of objects all pulling on the central state, where drives would pull towards a point.  
### Directional Drives
The drives acting upon the mind's state could act along a single direction, in which it would make the number of dimensions in the state and number of drives equal.  
### Aspect-based Force
Similarly to forces in nature, the drives could act upon specific aspects of the mind, like how EM, the weak force, and the strong force act upon charge, flavor, and color respectively.
This would open the door for certain dynamics.  
### Non-Euclidean State Space
The space of mental states may not necissarily be eucliean, and could be warped, and possibly describable by some sort of diabolical metric tensor.
### Potential Field
We could even have a potential feild like force that is local to state and drives the state to its low points.
That gradient Drive would be equal to the negative gradient of the potential taken along state space.
In that case it could be added to the net drive summation and could allow node-like transitions between states with drives that are not exactly alligned to the change because the potential could just funnel the state.
