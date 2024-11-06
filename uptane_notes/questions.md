# Questions

## Uptane standards meetings
### For Aug 13
* Does our current model work for modern (fifth generation/**zonal**) E/E architectures where everything is zone based? @Phil 
* Can someone explain the director role simplification topic brought up by Jon a couple of weeks ago? @Jon
  * relax the standards a bit
  * set up some specific requirements and define the threat models for the director, to see if we could get to an implementation of the director that wouldn't necessarily require the Uptane structures (not all of them). 
  * people coming and looking at Uptane, seeing the value of having something like the director role and the image repository structure but not going all the way to a director implementation, and using archs inspired by the director. 
  * could be because director implementation details 
    * timestamp and snapshot are not useful in the director metadata, can be considered optional _according to jon_
    * the vision and assumption (but is not codified in the standard) is that the director metadata should include all targets
    * in practice because of the way real world implementations look, director metadata often doesn't have everything
  * can imagine a simplification of director metadata along with a preamble explaining the purpose of the director to open up different interfaces to direct the installation of updates; he's not so convinced of the Uptane loop being the totality of the ota update loop to be like. 
  * director could be a bit more static? 
  * director generally needs to be taken away from business logic
* Can someone pls put me in touch with some contact in motorsport?
  * the thing about motorsport is that everything is very custom
  * fleet size is small
* One thing about aftermarket parts isn't only how we can provide updates, but also how to protect the OEM and the car against any funny business attempted by the aftermarket part. 
  * huge market for ECUs for cars which have reached EOL according to ira
  * 
* Can one primary ECU contact multiple directors? 
* Why is constrained delegation not possible in the Uptane standard?

### For Oct 8
* for the logger storage service, can it be stored on an hsm?
* For the logger process, what threats can be associated? can spoofing be associated with it considering the logger will be a process running on different devices, and not the device itself? how do signatures and certificates work for that?
* 


# Uptane community calls (fridays)
### For October 4
* If the onboard time source is interacting with the external time-server, it should have external network access right? Isn't it the case that the TCU has access to the network? tell me if im wrong
1. add logger process to vehicle trust boundary 
* how to take this forward
  * create attack trees
  * this will be an input to the TARA process - assets


# Meeting with Justin (wednesdays)
### For October 2nd
* What can be done to prevent an arbitrary software attack?
  * If the director repo gets compromised, then an arbitrary software attack is not of much concern, because that will be caught 
  * The situation where an arbitrary software attack is a concern is when the image repo gets compromised
    * For this, the root and targets keys need to be compromised, but those are offline keys.
* Elevation of privilege for primary - how can we ensure that the primary's core functionality of full verification doesn't get overridden?
* Where would a partial bundle installation attack go? on the primary or secondary?
* How should we take up the midsem report and stuff? Do you want it in a particular format? How would you grade me? 

### For October 9th
* Thanks for the grade
* Do you think we'll be able to get this into the standard? If not, where would you rather it go?
  * the most logical thing is for it to be a standalone document
* Did you submit it on the google form

### For October 16th
* I was thinking about adding delegations to the dataflow diagram and the threat model - creating a new one for it. Could you suggest some things I should keep in mind while modeling for that? Apart from that delegations only apply on image repo
  * you can delegate only part of a namespace
  * thresholds - 3 of these 5 ppl 
  * 
* Can you explain terminating delegations? 
  * 
* I realized that one change I have to do is I should ideally show multiple update images coming from the image repository and then all of them being packaged and shipped as one bundle. 

### November 6th
* Last in person meeting
* Did you get a chance to go through the [Google Doc](https://docs.google.com/document/d/1qvwMfmPXuJJko51OcnTHaV-s3GYYVfpgfMq_4CGSr5k/edit?tab=t.0#heading=h.jw29vkrdvnh9)?
  * 
* Would you be willing to write an LoR for me? Not immediately, but sometime in the near future?
* There's this [SAE conference](https://saeindia.zohobackstage.in/Automotive-Cybersecurity) in Bangalore November 22 and 23, on automotive cybersecurity. The agenda seems interesting, it is about TARA for charging ECUs and more importantly, discusses automotive cybersecurity standards in india. I think it could be a good opportunity to promote Uptane, network and get an understanding about Indian standards for automotive cybersecurity. I was thinking about going - Would NYU be able to sponsor my registration? 
  * It is 12,000 + tax ~= $170. I will manage the flight tickets and accommodation by myself.
  * Unfortunately cannot be done due to logistical issues. He would love to but cant.
  * Suggested bringing it up with the community
* I think I've been doing good work on gittuf - I've designed the high level idea about how the hooks distribution should work with Patrick, and i'm developing a PoC for it. Since I'm not getting any credit for it, I was wondering if I could get compensated for it. I remember in our first meeting you mentioned that I can't get paid and get credit for the same work but we can figure out a workaround if I do good work. This doesn't count as credit. What do you think?
  * Again, no because of logistical issues
* Also, if this is possible, i was thinking about maybe continuing being affilliated with NYU to work on gittuf and be on the payroll - it doesn't matter how much it is, but it would be nice. If you say no, I think I will still be open to contributing to it because I liked doing it.  