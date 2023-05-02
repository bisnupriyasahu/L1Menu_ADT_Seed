ADT seeds are based  on the score of anomaly detection algos. The threshold are exactly the value of the cuts on this score, called ASCORE.
Menu team creates the menu by using TME (xml, html), and Herbert takes care of the synthesis of the firmware of the menu provided by the menu team. The result is always an xml file, but in the name it has appended something like "-d1".

Herbert was providing the (ML@uGT devs) the menu xml (and html) files.
From Herbert, one cannot freely choose the NN score as a cut in the uGT. There is 1 NN for each score currently implemented.
Hence if only 20000 is there one cannot choose 21000 or so. 
Only to select whether a particular ADT network has triggered or not.


After implementing the seeds in TME one needs to provide different "external signals" to the seeds.

Both types are implemented with a workaround using "ext_cond signals" with the thresholds as part of the ext_cond signal name. This workaround is used as long as ADT and topo trigger objects are not in the UTM.



utm 0.11.x has full support for ADT objects using ASCORE cuts. Using external signals is just a workaround Herbert implemented for the first evaluation tests (it is still supported though but will be removed in future). However topological trigger seeds are only supported using the external signals workaround, until we add full support into utm with future releases. 

Documentation of utm 0.11.x can be found [here](https://globaltrigger.web.cern.ch/globaltrigger/release/utm/latest_doc/html/releaseNotes/v0_11_0.html)


currently one NN per ascore is implemented in the firmware. There is no difference in using utm's ADT.
It might be possible to optimize to generate only a single NN in future firmware versions.
