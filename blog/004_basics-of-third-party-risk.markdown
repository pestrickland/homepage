Tags: Third party risk
Date: 2012-04-21 21:45:00
updated: 2012-06-23 16:03:00
Title: Fundamentals of Third Party Risk Calculation
Slug: third-party-risk-2
Summary: As part of my personal project looking at third party risk, I outline some of the simplifying assumptions I have made to bound the scope of my study. By assuming that various failures have already occurred, my study is focused on modelling the at-risk population. Basic approaches can be used for this, but I am planning to use Monte Carlo simulations for a number of more complex scenarios, hopefully leading to more accurate predictions of risk.
status: draft

Calculating the third party risk associated with a weapon release is often quite involved. For each release there are a large number of variables that affect the outcome of the event. Some of those variables are known, but others are unknown or require an unfeasible amount of effort to determine.

This article discusses the fundamentals of assessing the third party risk associated with weapon releases. In particular I focus on weapon failures, for reasons I have [previously discussed]({filename}001_third-party-intro.markdown). The key points discussed here concern the assumptions made in order to simplify the assessment, and the use of population density to construct a model.

##The basic approach
Several events need to occur in order for a weapon to fail and for it to injure or kill a third party. To study every event in detail would require in-depth knowledge of the weapon of interest, especially if that weapon is guided. That is beyond the scope of this article, not to mention far too involved for what is effectively a "hobby" of mine. Such in-depth weapon knowledge is also not appropriate material for the open internet.

The following list is a simplified sequence of events that would result in the death of a third party in my scenario:

*  The weapon is released
*  The weapon fails to guide to its intended target
*  The weapon hits the ground and detonates
*  A person is within range of the weapon's damaging effects
*  The person suffers a lethal amount of damage

In terms of the probability of that event occurring, the following equation can be defined:

$$
P\left(\mathrm{kill}\right) = P\left(\mathrm{release}\right) \times P\left(\mathrm{fail}\right) \\
\times P\left(\mathrm{detonates}\right) \times P\left(\mathrm{hit}\right) \\
\times P\left(\mathrm{lethal}\right)
$$

This top-level equation requires the calculation of five separate
probabilities, some of which may be a combination of other probabilities and
events. In order to reduce the amount of work, some simplifying assumptions can
be applied.

###Assumptions
For the purposes of this study it can be assumed that the weapon in
question is always released. This makes sense due to the deliberate nature of
the release event. In terms of third party risk it also makes sense -- if the
weapon is not released, then there can be no risk to third parties
*associated with the release* (there may of course be other hazards, but they
are outside the scope of this study).

The probability of a weapon failure happening will hopefully be very low for
guided weapons. But it is a complex value to calculate; it is specific to
individual weapons and requires detailed knowledge of the weapons. Furthermore,
since I am studying risk specifically associated with weapon failures, rather than collateral damage, it makes sense to assume that a failure always occurs. Similarly, I will assume that the weapon always detonates on impact.

The final simplification I will make is that when a person is deemed to be
"hit" by the weapon, the effects on them are always lethal. Combining these
simplifications results in the following equation:

$$
P\left(\mathrm{kill}\right) = P\left(\mathrm{hit}\right)
$$

Obviously this equation is far simpler; all that is needed is to calculate the
hit probability associated with a weapon release.

##Determining the hit probability
Based on the above assumptions, the following scenario exists:

* The weapon has been fired
* The weapon has suffered a guidance failure of some kind
* The weapon has hit the ground and detonated
* If a person is within range of the weapon's effects, they suffer lethal
  damage

The unknown element of this scenario is whether a person is sufficiently close
to the impacting weapon to be considered as "hit". Two key factors affect
this probability:

* The density of the population in the impact area
* The range of the weapon's lethal effects

<figure>
<img src="/images/pop_density.png" title="Differences in population density">
<figcaption>With a lower population density on the right, it is less
likely that an impact (orange circle) will hit a person (blue circle).
</figcaption>
</figure>

The higher the density of the population, the more likely it is that a person is hit
by the weapon. A weapon that has a large warhead will cause damage over a
larger area than a weapon with a small warhead. A smaller warhead will
therefore need to hit closer to a person in order to have an effect.

<figure>
<img src="/images/warheads.png" title="Differences in warhead effects">
<figcaption>With a larger warhead, there is more chance of a person being
hit.</figcaption>
</figure>

###Population density
The calculation and modelling of population density will form the majority of
the work I write about. The actual density of population within the area that
the weapon will hit is what is required. Such information will be highly
dependent on the specific area where the weapon is released, and also the time
of day among other factors. Even if such information was available, it would
only be truly valid for that particular case. A more general approach can be
applied using a uniform distribution of population over the area of interest.

As a topical example, Afghanistan is listed in the CIA World Factbook[^1] as having
a population of 30.4 million and an area of 652,230 square kilometres, leading to
a population density of around 47 people per square kilometre.

With the population density known, the chance of the failed weapon hitting a person
can be determined using basic probability. But the application of such a coarse
calculation has some problems. With terrain that is mostly rugged mountains,
only 12% of the land classed as arable and 4% of the land as irrigated,[^1] it
is unlikely that the population is evenly distributed across Afghanistan. A more
appropriate model might be one where the majority of the country is sparsely
populated, with population concentrated in urban areas or areas that are
irrigated. Another consideration could be that the weapon might only be used
near centres of population. All this means that the low value
of 47 people per square kilometre for Afghanistan could indicate extremely
optimistic levels of risk when compared to the risk associated with the actual
population density.

###Weapon lethality
Warhead characteristics are another substantially complex set of elements to assess. There are a wide variety of different designs and sizes in use, ranging from the small shaped charge warheads used in variants of Hellfire[^2] and Brimstone[^3] to the large blast/fragmentation warheads found in the Mk 80 series of bombs[^4]. The effect of the warhead also depends on whether it detonates in the air, on the ground, underground, in a building, etc. In my study I will use simple nominal values for the lethal areas caused by the warhead. These might range from a circular area of 0.5 m radius -- e.g. if a direct hit is the only cause of lethality -- to 50 m radius or more for traditional blast/fragmentation bombs.

##Improving on the basic approach
Whilst the assumptions made above simplify the assessment, they also result in
crude approximations of the scenario being studied. In some cases this leads to
a pessimistic level of risk -- the actual risk is lower than predicted. In the
worst case, the predicted risk is optimistic, and there could be a situation
where the true risk is much higher. If this type of assessment was used to make
decisions about using weapons, clearly an optimistic model would be
unacceptable.

As stated above, I am focusing on the means of modelling the population. My
work will attempt to investigate the use of more complex models, by including
higher resolution population data and also considering factors such as the
presence of towns and the time of day. My intention is to use Monte Carlo
simulations to study many combinations of parameters that could affect the
population in an area in order to determine the variations in hit probability.
If possible, I will also investigate whether a generic model can be created
that is both simple to generate (given a few basic parameters) and also
relatively accurate.

##Summary
The assessment of weapon failures and the associated risk to third parties is
involved with knowledge of weapons, their effects and their failure mechanisms.
Knowledge of population distribution and density is also required.

I have made simple assumptions in order to reduce the scope of my study to that
of modelling the population at risk. Whilst a basic approach of taking
population data and averaging it over the area of interest can be carried out, I
am planning instead to use Monte Carlo simulations to calculate hit probabilities for
more complex population scenarios. If successful, I will try to create a
generic population model that can be used to create a more accurate prediction of risk.

##References
[^1]: Central Intelligence Agency, *The World Factbook*, available at
<http://www.cia.gov/library/publications/the-world-factbook/index.html>
[accessed 06 April 2012].
[^2]: GlobalSecurity.org, *AGM-114 Hellfire Modular Missile System (HMMS)*,
available at <http://www.globalsecurity.org/military/systems/munitions/agm-114.htm>
[accessed 21 April 2012].
[^3]: Wikipedia, *Brimstone (missile)*, available at
<http://en.wikipedia.org/wiki/Brimstone_(missile)> [accessed 21 April 2012].
[^4]: Federation of American Scientists, *Mk82 General Purpose Bomb*, available
at <http://www.fas.org/man/dod-101/sys/dumb/mk82.htm> [accessed 21 April 2012].

