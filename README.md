# IA301-Ontology-project
This ontology addresses one of the most important topics today - the health crisis linked to COVID-19. Its aim is to assess the dangerousness of places according to different factors and to track the spread of the virus in order to protect the population.

# Description of our ontology and a problem it solves
As we have just explained in the introduction, our ontology fits into one main subject, the Covid-19 health crisis. Protection of population from the virus is the highest priority and, nowadays, it has become the centre of our concerns. One thing that can help to prevent spreading of the virus as much as possible is to raise awareness of responsible behaviour so that the population is aware of the dangers. The identification of the places and clusters of contamination as well as their level of dangerousness is a key element in the fight against the virus. We assume here that we have the GPS data of the individuals as well as their status in relation to the Covid (positive or not). This ontology will therefore respond to the following problem, identification of potential contamination sites, as well as the level of risk for each site declared as potentially contaminating, according to the characteristics of the site.

# Justifications of our ontology design decisions
We have tried to reproduce a real environment. We consider a group of 15 people (than can constitute a cluster), each of whom carries out different activities in different parts of his or her place of residence (of course, we consider that these 15 people live in the same town).  So first we have a class Person with several persons in it and the first reasoning will be whether a person is dangerous (in the contaminating sense or not). In order to do so, we reasoned by grouping together all the people who are positive or who do not respect the barrier actions as potentially negative people. 
Then we have a class Place with subclasses (indoor_places, outdoor_places…) and we considered a property between places and person allowing to see whether a person visited a place or not and we naturally reason as follow, each place visited by a person who did not respect the barrier gestures or was positive to Covid, will be considered as an unsafe place and therefore a potential cluster place for the covid. 

Finally, based on the studies provided in these resources:

• https://www.huffingtonpost.fr/entry/coronavirus-situation-plus-ou-moins-a-risque- tableau_fr_5f4955abc5b64f17e 13d7bd8 

• https://www.gov.uk/guidance/new-national-restrictions-from-5-november 

• https://www.gouvernement.fr/info-coronavirus#:~:text=Dans%20le%20cadre%20du%20confinement,kilom%C3%A8tre%20autour%20de%20son%20domicile,

we have carried out a reasoning that estimates the level of dangerousness of each place, and to what extent these can be the origin of the cluster. 
Notice two things: 
	
  - We perform reasoning in order to “classify” places in a general way, (very low, low, medium…) in the classes we have formed based on sources from different countries (as it can be seen above).
	
  - The characteristics of the places initially instantiated are made again according to logic and sanitary restrictions and law implemented in the country (for example you need to wear face coverings at work in many countries nowadays). However, our ontology is enough robust to still characterize and give a level of risks, in a lot of situations where places are not following the common rules imposed by place (for example if we have a work place not respecting the face coverings rule) the reasoning will still allow to give a risk for this place which will be higher than expected in this place) as we have generic classes and reasoning to handle that.

Using ontology as described and implemented here, we were a able to perform a reasoning in order to define places that are more (or less) likely to be the origin of a certain cluster in the population, but also to understand which are the risky places to tell the population.

# UN SDG problem
The Sustainable Development Goals are the blueprint to achieve a better and more sustainable future for all. They address the global challenges we face, including poverty, inequality, climate change, environmental degradation, peace and justice. There are 17 different goals and one of them (the 3rd one) is Good Health and Well-Being. Its aim is to ensure healthy lives and promote well-being for all at all ages. It is not hard to notice that our problem (the problem which we are trying to address with our ontology) falls into this category as it completely aligns with the goal’s area and aim.

# Fixing ontology pitfalls found with OOPS! tool
We have run our ontology implementation through OOPS! – online ontology scanner and we did have some pitfalls that were marked as important. All 4 of them stated that there were object properties without domain or range (or none of them) included in the ontology. After analysing we found which four properties were and the problem and added missing domains and ranges for them (modifier_property, person_property, place_property and visit_property). Other than these there are just minor pitfalls that, as stated on the website, are not really a problem and would just make the ontology look nicer if fixed.
