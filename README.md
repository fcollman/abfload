# abfload 
This is a matlab function for reading abf 2.0 file formats.  
so far I have gap free recording working, but haven't finished the other modes.. though they shouldn't be too hard.


I would welcome people auditing the code.. i have attached in comments the information from the C file from axon I used to help decode the header information. 

You can get the C code yourself here 
http://www.moleculardevices.com/pages/software/developer_info.html

the original abfload can be found here 
http://www.mathworks.com/matlabcentral/fileexchange/6190

This is still a work in progress.

--------- 
updates 
--------- 
Harold Hentschke, the original author of abfload fixed a couple bugs and cleaned up the code, 
and i am updating this version to include his changes which are: 
- fixed a bug regarding the fADCSampleInterval being incorrectly set 
- restructured the code so it's easier to see which portions deal with which ABF version 
- incorporated all accessory functions as subfunctions 
- changed the number type of 'fFileVersionNumber' back to floating point 
- updated the copyright note 
--- 
Further updates from Forrest Collman: 
-added support for reading in tags, both in abf 1.0 and 2.0 format 
-fixed bug associated with reading in files created in axoscope. 
-fixed a bug with my tag support, i had assumed there were tags to be read, should work now on either.

---updates from Harold (06/2011) 
bug fixes:

- in the precursor version (abfload) there was a potential problem in the gap-free reading mode: in exceedingly rare cases an error resulted when reading data, namely when division of the number of points by 'chunkPtsPerChan' (see input variable 'chunk') left no remainder

- abfload would only recognize abf files recorded from some of the Axon/MolDev programs (clampex & axoscope). This was due to an incomplete list of programs listed in variable 'progString'. abfload should now read data produced by clampex, clampfit, axoscope and patchxpress

- changes to the tag section which hopefully cover all of the reported problems

other changes:

- some restructuring of code for better oversight and/or in conjunction with bug fixes, modified comments

- data in 'high-speed oscilloscope' mode can now be read (in addition to the two other waveform fixed-length modes)

- right below H1 there is a 'PROBLEM CASE REPORTS' paragraph in which very specific, as yet unresolved problems with abfload (and recording abf files in general) are listed, which may help resolve related issues
