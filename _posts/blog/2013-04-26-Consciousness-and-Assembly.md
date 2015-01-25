---
layout: post
title: Consciousness and Assembly
categories:
- blog
---

The instructions that your computer's central processing unit
(CPU, the "brain" of your computer) uses to accomplish what you
ask it to might be revealing about how your flesh and blood brain
work.

### How I came to the idea

I have started to read Jean Paul Sartre's [*Being and Nothingness*](http://en.wikipedia.org/wiki/Being_and_Nothingness),
and it is proving very rewarding. I chose to begin reading it for two reasons:

1. I spend a lot of my time coding for class and for myself, but I only ever read for philosophy class, so I'm doing some outside of class philosophy work; and
2. Existentialism is famously known to be a humanism, and I get the impression that (and this may be totally wrong) it is an inspirational breaking down of human psychology in this vast, scary Universe probably devoid of meaning or purpose, and I could use this right now.

But I am find myself a little nervous and skeptical while reading it.

Jean Paul Sartre and the existentialist movement place a lot of importance on and argue strongly for free will. Making choices is something central to their understanding of the human mind and reality.

I am convinced they are wrong, and find the arguments for hard determinism to be valid. 

[Hard determinism](http://en.wikipedia.org/wiki/Hard_determinism) is the belief that given all the information about the speed, location, etc, of all the atoms and sub-atomic elements in the whole Universe and a sufficiently sophisticated understanding of how they interact, a mind could predict with 100% certainty what would happen in the future.

What more, but the objections to hard determinism do not lead to free will, but rather that we are only captive to the random tendencies of the matter which our mind is composed of. When Sartre is deep into explaining how anguish is the human emotional response that is generated when we notice the possibility of our non-existence and/or the non-realization of some desirable goal, and our continued choice to be and to do is to escape this anguish, I find myself both inspired and in agreement ...

But ultimately disagreeing. And I can explain why with computer science.

### Programming, assembly language, and machine code

All of the software you use on any of your digital devices, like your phone's text messaging application or Microsoft Word, are programs, they are defined by *code*. It all looks something like this:

	a = 5
	b = 7
	c = b + a
	output(c) 

This program "outputs" the value 12.

Everything your programs are executed on the CPU using 0s and 1s, this is [*machine code*](http://en.wikipedia.org/wiki/Machine_code). It all looks something like this:

	0101010001000100100

And at a slightly higher level, these numbers can be defined by hex values, base-16 instead of the base-2 of the 0 and 1 flavor of machine code. It looks like this:

	af ff 0a b3 f5

These are all just numbers. Data. `ff` in hex, for example, is the decimal number $255$. That binary number up top, all of it, is the equal to the decimal number $172,580$.

> Wait! How does what I see in Word get defined in "code" that is ultimately made into just ... 0s and 1s ... How does my computer know what they "mean"?

The way that Word is made with code is with just more complex versions of the first example, where programmers make something like a "document view" program to build what you see, a "document model" defining how it is that your pages can look and how they are stored, and perhaps some sort of in between program that dictates how what you see interacts with what's stored. 

The way that your computer knows what 0s and 1s mean is by design! Clever scientists design a chip with a lot of densely packed on-off switches, and when the switches are turned on and off in a certain way, it triggers other on-off switches to go on or off in a predictable way. Furthermore, all the switches can be observed, so when you flip the switches, you can look at the "answer switches" to determine what happened.

> Okay, I *just about* get it. But ... uh, how does code become 0s and 1s?

With [**assembly code**](http://en.wikipedia.org/wiki/Assembly_language)! Assembly is the human-readable intermediary between programming languages and CPU "on-off" instructions. Assembly code is defined by the people that make your CPU, and that definition is used by people that make programming languages. 

And now you see how everything links up. You have MS Word, which is made with a high-level programming language. This is converted into assembly code for a given type of CPU. This assembly, in one way or another, is made into zeroes and ones.

Observe that your programs, your MS Word, is eventually just made into numbers, in data. That you programs are composed of the same stuff as the content you type into your Word document - values, content, data. [Programs are data](http://c2.com/cgi/wiki?DataAndCodeAreTheSameThing).

And this is a model I can use to reject free will.

### How this all relates

It is in the common parlance and every introduction to technology textbook that the CPU represents the "brain" of a computer. The simile is a useful one because it actually represents the way that these things are. A CPU is used to make decisions about how your computer should operate in the same way that we have come to believe that the brain is the organ used to make decisions.

But these are never really decisions, they are merely computations.

When writing code, it is an illusion that your program is any way unique from a given set of numbers. It is a useful illusion that allows a programmer to extend the possibilities of useful and meaningful combinations of numbers to be fed to a processor.

I think that likewise, when making decisions, it is an illusion that your "decision" is any different from other types of events. The world-view of the determinist is one of events. Every event is preceded by the necessary prior events and followed by the necessary and inevitable future events. When a rock is triggered to roll down a mountain by a strong wind, the event is composed of a relatively large series of atomic events that let to its happening. With a sufficient understanding of the present condition, it would be possible to predict that the rock would be made to move. A meteorologist, geologist, and physicist could work together to accurately predict the weather, the threshold for moving the rock, etc.

In this metaphor, events are just "values", just numbers. They represent a state of reality. I predict that as we learn more and more about smaller and smaller particles, that there will be some level at which either there is something or there is nothing. The aggregation of these atomic somethings and nothings forms progressively larger collections of somethings or nothings. Atoms represent a certain collection of somethings and nothings in that there is the "something" we have called the nucleus, the "something" we call the electrons, and there is the "nothing" in between the two groups. Additionally, a nucleus is composed of two types of "somethings", protons and neutrons. We are finding that those are composed of there own types of "somethings", which we presently do not know much about, but they are called sub-atomic particles.

I believe it is inevitable that there is some level of somethingness and nothingness which is atomic (not to be confused with atoms, which we now know are not atomic - whoops, Western science jumped the gun with that naming convention). Somethingness and nothingness can be thought of in terms of the binary number system, where one is something and zero is nothing. If you can assign this level zeroes and ones, you can assign progressively larger values to the aggregates of this something or nothingness. 

If this is true, then all states of reality, all aggregate compositions of somethingness and nothingness can be assigned a value. Reality is data.

This would have consequences for the brain because it would mean that states of the brain, the configuration of a brain when it is holding a belief or performing an action, can also be reduced to values. 

From the perspective of the brain, and admittedly I do not understand this at all rigorously, somethingness can be thought of as a neuron being "on" and nothingness can be represented by the neuron being "off." In a series of firings of electrical impulses, states of the brain change. When you feel pain, neurons send "somethings" up to brain, and that changes the configuration of the ons and offs in a particular way, and you respond accordingly.

Furthermore, when you are presented with a decision, your brain gathers information about the decision using your perception, your sense organs. This is stored and is accessible. Using some decision making function, you appear to come to some conclusion and you enact it. 

States of reality, under this model, are values. States of your brain and the beliefs and processes those states represent, are values. As physicists decode the language of reality and as neuroscientists decode the language of the brain, I predict that we are going to become increasingly aware that the Universe and our brains are complex machines. With this realization it will become increasingly clear that just as code being unique from data is an illusion, it is also an illusion that events in world are unique from states of reality, and it is also an illusion that decision-making is unique from the states of the brain.

This is exciting because it means as we come to understand the machines we make more and more and as they become more sophisticated, it will be revealing about the machine that makes and understands these increasingly sophisticated machines. Furthermore, as we come to understand the machine that we are more and more, we will be able to produce increasingly better reproductions of thinking.
