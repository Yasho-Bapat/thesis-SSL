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


# Uptane community calls (fridays)
### For October 4
* If the onboard time source is interacting with the external time-server, it should have external network access right? Isn't it the case that the TCU has access to the network? tell me if im wrong

# Meeting with Justin (wednesdays)
### For October 2nd
* What can be done to prevent an arbitrary software attack?
* Elevation of privilege for primary - how can we ensure that the primary's core functionality of full verification doesn't get overridden?
* Where would a partial bundle installation attack go? on the primary or secondary?
* How should we take up the midsem report and stuff? Do you want it in a particular format? How would you grade me? 
