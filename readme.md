# Time travel

This is a computer game that aimes to use timetravel in a meaningfull and consistent way. 
The idea is to abstact the situation and let it evolve passible, while when the player arrives at a certain
time, the passive run of history is stopped (also time stops running, for the demo. in the full version we will find a way
to run history while in an active situation). Players can change some situations, and can time travel to other parts.


##History
History contains a set of rules that govern how states evolve. Each 


Changes that a player makes are also abstahated, and when a situation in a certain time is created, it will run the 
algoritm and each time it arrives at a moment the player influenced, it will try to apply the change. 
If this is impossible, it will create a so called paradox. For example if you go to 1875 and kill a person, and 
then go to 1850 and kill his father (before he had children). Afterwards you go to 1900, the history algoritm will try
to do the following:

- 0-1850: run history normally
- 1850: kill personB
- 1850-1875: run history normally
- 1875: ERROR, personA does not exist. IGNORE
- 1875-1900: run history normally.
- 1900 load state.


But for example is you convince a person that will be killed later by you to change it's profession, time will try to heal
itself and he will still die by you're hand. This does not apply is he for example was a carpenter and died in an accident,
then if you change his profession, history will evolve differently. 

Is is quite important that the algoritm is deterministic, so that each time history is run from a certain point, 
as long as no changes are forced, history runs exactly the same way. It is also important that little changes will
create little differences when run from a certain time, so not have the butterfly effect, (except for maybe long times)
This prevents the use of randomness, even when the seed is saved, as a small event may cause an extra call to a random-
event generator changing the outcome of all random event generators.

###State
An state contains different form of data

- all living people
  - a person has a 
    - name / gender / birthdate
    - from age of 16 -> a profession
    - from age of 20 -> a spouse
    - fluid -> an amount of status
    - maybe money ( but for now they are communist)
- all materials
  - food  (farmer)
  - building (for buildings) (miner)
  - luxeries (jobkeeper)
  - progress (scientist)
- inventions
  
  
### people

People all have an id string. The first people created on state zero all get a letter. Children of them get id's like this
- first child (<father><mother>)
- second child \[<father><mother>\]
- tirth child {<father><mother>}

People evolve like the following algoritm

If they become 16 years old they select a job. 
-> During shortage of material -> job that produces material (in order of food/build/lux/science)
-> otherwise, job of parent with highest status. 

If they become 20 years old they select a spouse
-> should be between 18 and 25 and different gender
-> lowest difference in status.
If impossible-> try again
-> spouse also gets spouse




##Setting and backstory

It happens on a small rock floating in the void. This setting will explain the availability of time travel, and
also will limit the amount of people/materials/professions/... in the game. 