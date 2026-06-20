---
layout: post
title: A Metaphysical model of Psychology
date: 2026-06-20
---

# A (Meta)physical Basis for a Model of Psychology
I have recently begun designing a tabletop roleplaying game inspired by D&D, GURPS, and Disco Elysium. I wanted a system that had a strong focus on the mind, so I set off trying to model the mind first, then simplify it later into game mechanics. This has quickly become a very complicated undertaking and is not yet complete. Here is the current state of said model.

## Inspirations
In order to make my model the first place I looked at was psychoanalysis, specifically Drive Theory from Freud as well as Jung in general. I was not satisfied with Freud’s two drives of Eros and Thanatos, so I iteratively altered them, split them, and interviewed people about their experiences. My criteria for selecting the Drives was that it was not a mental State (i.e. an emotion) and it was not a Capability (i.e. perceptiveness) and to merge things if logical. It is important to keep in mind that Drives can create emotions, but in both a positive and negative way. An example of this is Techne (described below) creating both feelings of anxiety and satisfaction. I eventually settled upon 5 drives and 2 supporting phenomena.

### Thanatos (The Survival Drive)
Thanatos is the drive that pulls you to act, usually destructively and out of the social order.
In survival situations this drive made sense, as bringing oneself to fight other humans and to hunt animals requires a level of emotional dulling.  Thanatos can manifest in such ways as finding satisfaction from watching destruction (e.g. gawking at a demolition) to palpable fear and the “call of the void”.

### Eros (The Bodily Drive)
Eros is the bodily urges and desires: Libido, hunger, boredom. This is probably the most straight forward Drive, creating feelings of desire, satiation, spoiled moods, and anger.

### Mania (The Hubris Drive)
Mania is both a very egotistical Drive and a very power-hungry drive. Power fantasy, and manic feelings arise from it, as well as feelings of narcissism, authority, and humiliation. 

### Techne (The Diligent Drive)
Techne drives the desire to create crafts, solve problems, seek order, and learn things. It often creates feelings of satisfaction or anxiety.

### Psyche (The Soul Drive)
Psyche drives introspection, actualization, sociality, and connection. 
This one's the most complex, but I couldn’t bring myself to split it as the feelings produced by the euphoria of self-discovery and of oneness with someone else is quite similar. Though I can see the argument to split Psyche on inwards vs outwards lines.
Psyche in negative expression gives lonely, lost, or dysphoric feelings, and in positive expression often gives feelings of agape or platonic love, euphoria, and fulfilment.

### The Two Supporting Phenomena
From Freud I found that his idea of [Overdetermination](https://en.wikipedia.org/wiki/Overdetermination) worked really well to describe strongly entrenched mental states that are driven by multiple sources. And from Jung I found [Possession](https://junguipediaeng.miraheze.org/wiki/Possession) to well describe when a single drive completely takes over a mind (i.e. Techne possession manifesting as the flow state)

## Setting a Basis

Continuing further, I wanted to formalize this model into something more metaphysical or mathematical. This seems initially odd for something so subjective, though I argue that the mind is like a fractal. It emerges from math, and that at all layers of abstraction, projection, and all phase spaces we still see math apply. Logically speaking, no matter how many layers of abstraction we go down some form of math should apply, so via emergence and reduction we can link the physical realm of numbers to the mental realm of forms.  
First, we must describe the state the mind takes. It clearly is multi-dimensional and has multiple states it can take. I figured that representing it as a velocity works well to describe its behavior, as the mind only exists meaningfully over time and when perturbed by a force the mental state moves without drifting unlike position which when acted upon would continue to drift until acted upon again. So I will denote the mental state as a vector:  
$$ \overrightarrow{S} $$  
The space of mental States may not be Euclidean, as knowing for sure would require knowing the properties of paths between mental States.
This space of states may have some sort of potential which guides the state into low points of stability via a force equal to the negative gradient of the potential over State space.  
$$ \overrightarrow{D}_{grad}=-\nabla \Phi(\overrightarrow{S}) $$  
This would make it so that, assuming that the mental State space is continual and not a large network of possible states, Drives that are not exactly aligned to a state transition could guide the State to a specific destination, like guardrails.  
Acting upon the State are the Drives, which may include the gradient drive. Taking a weighted sum of the drives (weighted for the sake of being safe) gives us a net Drive for j Drives:  
$$ \overrightarrow{D}=\sum_{j}^{}\overrightarrow{D_{j}}\omega_{j} $$  
We may also quantify how much the Drive moves the State via an inertia like term called Capability. Capability may be locally variable and may be a vector that forms an inner product with Drive but that’s just a maybe, it is easier to use in a discrete manner similar to mass.  
We may then create a formula analogous to Newton’s second law that relates Drive to the change in State:  
$$ \frac{d\overrightarrow{S} }{dt}=\overrightarrow{D}c $$  
Which can be made much easier to work with by switching to its discrete from:  
$$ \overrightarrow{S_{1}}-\overrightarrow{S_{0}}=\Delta t\overrightarrow{D}c_{0\rightarrow 1} $$  
## Applications of this Model
### Startle response
Starting at State 0 (some initial State where you notice something) and via some fear-Drive like Thanatos, it moves to State 1 (the startle State).
We know that the jump from noticing something to full alert is a big one, so we can assume that the difference in state is large. Additionally, we know that this occurs over a very short period of time. From these two things we can use our equation to say that either this driving force is very strong and/or the capability to become startled is very high.
### Waking up
We could think of someone in deep sleep. An external stimulus acting as a Drive pushes the State away from its state. It may be too weak and eventually runs up against the gradient Drive, no matter how long you wait, a qualitative state change won’t occur. Only when that stimulus becomes great enough so that the environmental Drive of the stimulus overcomes the gradient Drive, will we see the State move. In order to see that qualitative change of going from asleep to awake, the time required for that change directly depends on the magnitude of the drive, making a loud bang which produces a large stimulus shoot you awake quickly.
## A Larger Structure.
While this serves as a solid basis to understand the way the brain's state changes, the larger structure of the mind is uncertain, we may ponder in what way the mind may be structured. 
### Network of Objects
The mind may be a big network of objects all pulling on the State, where drives would be the result of objects directly pulling on, and interacting with the state.  
### Cardinal Drives
The Drives may act upon the mind's State along a single dimension. This would make it so that the dimensionality of the State would equal the number of Drives.  
### Property-based Force
Similarly to forces in nature, the drives may act upon the State relative to its internal properties, like how electromagnetism, the weak force, and the strong force act upon matter via their charge, flavor, and color respectively.
