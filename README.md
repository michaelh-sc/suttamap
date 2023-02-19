# suttamap
Buddhist Sutta metadata produced in a boring way by code, with much help from other code and LLMs.

All of these need to be checked rigorously before being treated as absolutely correct (it will not be correct). This is alpha, unuseable in production and data structures may change.

Currently, DN and MN identification of speakers of anything in double-quotes, identification of other people present, and where events took place exists here only in the data folder. 

Known issues:
 - Sometimes (e.g. DN13) single quotes denote speech and enclose double quotes for posed interlocutors so the data is incorrect presently.
 - Identification of people spoiken about within quotes is handled by simple Named-entity Recognition currently which misses things.

AN and SN forthcoming once some issues are resolved as the location of parts of AN is hard to guess, and many parts of SN and AN contain quotes that are implicitly the Buddha. Snp, Thig and Thag have their own wways of identifying speakers too.

Enumeration of certain kinds of lists forthcoming, each of which are to be checked by hand.

Actual python code forthcoming.
