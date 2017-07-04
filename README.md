# abfload 
This is a matlab function for reading abf 2.0 file format from Axon Instruments.  It is written in 100% pure matlab, so it should work on any operating system, a critical feature missing from the .dll based solution provided by Axon Instruments.

# contribution policy
We are open to accepting issues and pull requests from the community, or adding folks as contributors who become significant developers.  It would be most helpful if issues included links to specific publically available abf files which are designed to be the smallest file which reproduces the issue you are seeing.  These files could then be used to develop a test suite to automatically check that future versions of the code don't break reading the file in the manner desired. 

# project history
The abfload was originally written by Harald Hentschke and contributed on the mathworks file exchange.  In 2007, Forrest Collman edited the structure to accomodate the new abf 2.0 file format, by translating the pure C implementation into Matlab.  Since then, Harald and Forrest have both contributed to the codebase on mathworks file exchange with input from the comments section of Mathworks.  In 2017, the project was moved to github in order to encourage community contributions and facilitate collaboration between anyone interested in the project.

# issues, unsolved bugs
- code for reading user list section is incomplete (see variable UserListSec)
- June 2011: In one specific case, a user recorded data with a recording protocol that may have been set up originally with pClamp 9.x. In this protocol, amplification of the signal via a Cyberamp (the meanwhile out-of-date analog programmable signal conditioner of Axon Instruments) had been set to 200. Internally, this registers as a value of 200 of parameter h.fSignalGain. However, over the years, the setup changed, the Cyberamp went, pClamp10 came, and the protocol was in all likelihood just adapted, leaving h.fSignalGain at 200 (and the data values produced by abfload too small by that factor) although the thing wasn't hooked up anymore. However, when openend in clampex, the data are properly scaled. So, either the axon programs ignore the values of h.fSignalGain (and h.fSignalOffset) or - more likely - there is a flag somewhere in the header structure that informs us about whether the gain shall apply (because the signal conditioner is connected) or not. At any rate, whenever you change hardware and/or software, better create the protocols from scratch.

# to do list
- the header structure (output argument h) of files recorded with abf version <2.0 is quite incomplete compared to that of that of files with abf version >=2.0. Add code to have both as similar as possible
- set up test data & Matlab test suite
