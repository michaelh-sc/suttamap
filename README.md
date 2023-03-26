# suttamap
Buddhist Sutta metadata produced in a boring way by code, with much help from other code, LLMs and checking by hand.

All of these need to be checked rigorously before being treated as absolutely correct (it will not be correct). This is alpha, unuseable in production and data structures may change. Once everything is checked, the warnings will be removed from the _comment keys in json files.

Inside the data/ folder is for Digha Nikaya, Majhima Nikaya, Samyutta Nikaya and Anguttara Nikaya:
- Identification of speakers of anything in double-quotes
- Identification of other people present
- Who and where else is mentioned inside any double quotes - done by simple Stanford NLP NER
- Where the sutta's events took place, and if present, the geographical name as it is spelled in the DPPN on SuttaCentral.
- Lists (currently very spotty, will need to re-do) consisting of:
  - Comma-delimited lists
  - Sections of text repeated with a small change for each iteration
  - Causal sequences/chains or things described
  - Sections of text with lists between "..."

A single dictionary with the geographic coordinates, text from sutta, and the SC DPPN headword for all suttas in the 4 Nikayas.

Known issues:
 - Identification of people spoken about within quotes is handled by untrained Named-Entity Recognition currently using Stanford NLP (stanza) which can miss things not capitalised and mix up locations and people sometimes.
 - Some quotes have been missed, often large quotes. AN and DN have been manually fixed, MN and SN forthcoming.
 - Some geographical locations are missing.

Snp, Thig, Thag, others likely forthcoming.

Actual python code forthcoming.
