# Slimming down the Director Repository

### Why is this a good idea?
* How the director works is sometimes a barrier to uptane adoption
* What if it was just an http server or some server on an mqtt bus?
* we still have a bunch of stuff in Uptane that assumes that a repo is just a fileserver
  * irl that is very often not the face
  * that can be the case for the image repo, but not that much for director
* Director is more on-demand
* the director has two functions that are very distinct
  * one half is ingest, validate and process manifests
  * the other half is generate metadata about images to be installed
    * snapshot and timestamp are not necessary according to jon
* the contents of the metadata needs to be reevaluated. 
<br>
* what do we lose if instead of going through rotations, if we say that the user can rely on active ocsp responder or something like that?

* **look into SCA, CRL, x509, TLS**
* if we an construct a system that just uses regular PKI and gives us a similar level of protection that Uptane does for the director's functions
* maybe an addition to the standard as an alternative implementation of the director
<br>

essentially he's saying change director root metadata to x509 or tls certificate
* because of the ondemand nature of the director repo, there are no offline keys

* phil saying we should do a formal TARA for threat modeling before doing anything else
  * some things mentioned are more _goals_ than threats
  * we have an attack model but we don't have a matrix that says this part addresses this part
* can't see a strong argument that the structure of providing root and targets metadata is sureshot better
<br>
* look at making partial verification better
* 