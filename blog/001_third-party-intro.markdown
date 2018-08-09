Tags: Third party risk
Date: 2012-03-19 21:09:00
updated: 2012-03-19 21:09:00
Title: Air Power and Third Party Risk in Wartime
Slug: third-party-risk-1
Summary: In modern warfare, the risk to third parties posed by airborne weapons has become more and more visible. I have a particular interest in assessing third party risk, and am studying ways that it might be improved. Here, I explain what risk and risk mitigation are, and how I distinguish between third party risk and collateral damage. Finally, I introduce my aim of developing a generic means of assessing third party risk for the scenario of airborne weapon delivery. Whilst accepting that war cannot be made completely safe, I am keen to develop the best tools to allow accurate calculations of risk to be made.
status: draft

The risk to third parties associated with the use of airborne weapons is
something that has become more important in recent years. With the prevalence
of 'smart' or precison-guided weapons, there is a perception that
war can be conducted with such surgical precision that civilian deaths --
often called collateral damage -- are a thing of the past. That is
something that is certainly strived for, and modern guided weapons are
extremely accurate and increasingly have reduced yield in order to
reduce unnecessary destruction. However, the risk to civilians is ever-present,
and media reports of accidents involving civilians still occur with alarming
frequency, with a nine percent increase in civilian deaths during air strikes
in 2011 compared to 2010.[^1]

Assessment of third party risk is something that I am particularly
interested in. It is not without its problems, however, and over the last year
or so I have been thinking about how I could develop better tools and
techniques for assessing that risk. This is the first in what will be a series
of posts I write that will document my work. Most of the concepts I discuss
will be generic in nature -- discussing specific cases is difficult due to the
security aspects associated with defence work. Where examples are used, most
will be based around the approach to safety in the UK Ministry of Defence.

##What is third party risk?
Although there are more specific definitions, third parties can be
generally described as members of a population who are not directly involved
in a particular military operation. Therefore civilians are third parties, and
friendly forces in the area not directly involved with the operation can also
be included. In my area of the UK defence world, third party risk has the most
stringent acceptability criteria associated with it. In other words, the
'acceptable' level of third party risk is lower than that acceptable for first
parties (e.g. aircrew in the case of airborne weapon delivery) and second
parties (those with a supporting role in the operation). As an example, for the
risk to first parties to be tolerable, the probability of death per annum must
be no greater than 1 in 1000; for third parties it must be no greater than 1
in 10,000.[^2]

It is worth briefly discussing how *risk* is defined. It is essentially the
product of the probability of a hazard occurring and the severity of that
hazard. In the scenario I am studying, the *hazard* is death or injury caused
by failure of a weapon to guide to its target. The *probability* of this
occurring is simply how likely it is for the hazard to occur, whilst the
*severity* of the hazard is the consequence of that hazard occurring. In this
case, the severity would typically be categorised as 'catastrophic'. Risk
matrices are used to categorise risk in terms such as unacceptable, tolerable
and broadly acceptable.

###A note on collateral damage
Collateral damage[^3] is a term that gets used quite often when referring to the
death or injury of civilians/non-combatants, and the destruction of their
property. It is incidental to a particular attack against an enemy -- damage
that was not intended.

The Geneva Convention discusses the protection of the civilian population,
effectively minimising collateral damage by prohibiting indiscriminate
attacks.[^4] Military planners go to great lengths to minimise collateral
damage, by exploiting intelligence about the target and the local population,
utilising damage models and may even choose the time of day of an attack to
reduce the risk to civilians.

The work I am interested in is **not** predicting collateral damage. In my
paid job, we focus on the hazards associated with system failures, rather than
the consequences of a fully-functional system. In other words, we look at the
relatively rare events of system failure. The distinguishing point is that
*third party risk is not collateral damage*; a weapon that fails to guide to its
intended target could impact at random within a large area. It would be
unfeasible for planners to estimate collateral damage in an area of hundreds of
square kilometres. So, what I am interested in is creating an improved means to
predict the risk to third parties associated with events such as missile
guidance failure.

##Risk mitigation
All identified hazards have a risk associated with them, and a great deal of
effort is spent trying to reduce that risk. Risk can be reduced by reducing the
severity of a hazard, or by reducing its probability. In many cases the severity
cannot be reduced, and so the risk can only be reduced by decreasing its
probability.

In peacetime, the third party risk associated with weapons is well mitigated by
procedure. Live weapons are only carried on certain occasions, and all flights
are planned to minimise the overflown population. Weapon releases are even
rarer, and take place only over an air weapons range that is kept clear of
people. By taking these precautions, the risk to third parties is reduced to as
low as practicable.

In times of war, such stringent risk mitigation measures are not always
possible. Although weapon releases are still relatively rare and undertaken
after careful thought and planning, they do happen. Often, they are a last
resort, and necessary in order to prevent a greater loss of life than could be
caused by the weapon itself. But they still occur in areas where there **is** a
risk to third parties.

###Smart weapons are still dangerous...
Modern precision-guided weapons are incredibly accurate. Often equipped with
laser and radar seekers, GPS and inertial navigation, accuracy can be measured
in metres, if not less. Such smart weapons are also highly complex, and
very expensive. With weapons such as these being complex systems, there is
potential for them to fail in many ways. Hardware failure, software errors and
human error can all contribute to a weapon failing to perform correctly. The
probability of failures like this is incredibly small, with reliability targets
set as low as one failure in a million firings. But since failures can still
occur, they must be assessed in order to determine the level of risk to which
third parties will be exposed.

###...and not all weapons are smart (yet)
Whilst the fast jet aircraft of today can often be seen carrying smart
weapons, there are plenty of 'dumb' weapons being used too. From infantry
rifles to helicopter-mounted miniguns, and from mortar-launched parachute
flares to cluster bombs, there are plenty of hazardous munitions being used on
a daily basis.

##Summary
As an introduction to one of the projects I have been working on recently, I
have discussed how *risk* is the product of the *severity* of a *hazard*, and
its *probability* of occurring. I wrote about how risk can be mitigated by
reducing the likelihood of a hazard occurring or reducing its severity. The
importance of risk assessment in military activity was discussed, as was
collateral damage and the difference between it and third party risk.

I am interested in developing a generic means to assess the risk
associated with any type of munition in use. I don't suggest that a risk
assessment should be undertaken for every bullet fired, or any time that a
flare might be released. War **is** dangerous, and I don't think anything can
change that. But where there are situations that require risk to be quantified,
I would like to know that I have the best tools at my fingertips to carry out
that assessment.

##References
[^1]: United Nations Assistance Mission in Afghanistan, *Afghanistan, Annual
Report 2011, Protection of Civilians in Armed Conflict*, February 2012,
available at:
<http://unama.unmissions.org/Portals/UNAMA/Documents/UNAMA%20POC%202011%20Report_Final_Feb%202012.pdf>
[accessed 12 March 2012].
[^2]: Military Aviation Authority, *Gen 1000 Series Regulatory Articles, RA 1210 -- Management of Operating Risk
(Risk to Life)*, Regulatory Article 1210 Initial Issue AIL 1, 4 July 2012,
<http://www.mod.uk/DefenceInternet/AboutDefence/CorporatePublications/AirSafetyandAviationPublications/MAA/1000Series/>,
[accessed 18 March 2012].
[^3]: Merriam Webster, *'collateral damage'*,
<http://merriam-webster.com/dictionary/collateral%20damage> [accessed 11 March
2012].
[^4]: International Committee of the Red Cross, *Protocol Additional to the
Geneva Conventions of 12 August 1949, and relating to the Protection of Victims
of International Armed Conflicts (Protocol I) -- Article 51*, 8 June 1977,
available at: <http://www.icrc.org/ihl.nsf/WebART/470-750065> [accessed 11
March 2012].
