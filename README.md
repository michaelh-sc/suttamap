# suttamap
Buddhist Sutta metadata produced in a boring way by code, with much help from other code, LLMs and checking by hand.

All of these need to be checked rigorously before being treated as absolutely correct (it will not be correct). This is alpha, unuseable in production and data structures may change.

Currently, DN, MN, SN and AN identification of speakers of anything in double-quotes, identification of other people present, and where events took place exists here only in the data folder.

Known issues:
 - Sometimes (e.g. DN13) single quotes denote speech and enclose double quotes for posed interlocutors so the data is incorrect presently.
 - Identification of people spoken about within quotes is handled by simple Named-Entity Recognition currently using Stanford NLP (stanza) which misses things.

Snp forthcoming.

Enumeration of certain kinds of lists forthcoming, each of which are to be checked by hand.

Actual python code forthcoming.
