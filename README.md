# abfload 
This is a matlab function for reading abf 2.0 file format from Axon Instruments.  It is written in 100% pure matlab, so it should work on any operating system, a critical feature missing from the .dll based solution provided by Axon Instruments.

# contribution policy
We are open to accepting issues and pull requests from the community, or adding folks as contributors who become significant developers.  Please see issues tab for existing known issues and to report new ones.  It would be most helpful if issues included links to specific publically available abf files which are designed to be the smallest file which reproduces the issue you are seeing.  These files could then be used to develop a test suite to automatically check that future versions of the code don't break reading the file in the manner desired. 

# project history
The abfload was originally written by Harald Hentschke and contributed on the mathworks file exchange.  In 2007, Forrest Collman edited the structure to accomodate the new abf 2.0 file format, by translating the pure C implementation into Matlab.  Since then, Harald and Forrest have both contributed to the codebase on mathworks file exchange with input from the comments section of Mathworks.  In 2017, the project was moved to github in order to encourage community contributions and facilitate collaboration between anyone interested in the project.

# to do list
- the header structure (output argument h) of files recorded with abf version <2.0 is quite incomplete compared to that of that of files with abf version >=2.0. Add code to have both as similar as possible
- set up test data & Matlab test suite
