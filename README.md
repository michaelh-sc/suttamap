# suttamap
Buddhist Sutta metadata produced in a boring way by code, with much help from other code, LLMs and checking by hand.

All of these need to be checked rigorously before being treated as absolutely correct (it will not be correct). This is alpha, unuseable in production and data structures may change. Once everything is checked, the warnings will be removed from the _comment keys in json files.

Inside the data/ folder is for Digha Nikaya, Majhima Nikaya, Samyutta Nikaya and Anguttara Nikaya:
  - speakers/ Identification of speakers of anything in double-quotes in data/speakers single segment per speaker of each matching bilara's format.
  - speakers_locations: speech expressed as ranges, as well as:
      - Identification of other people present or mentioned
      - Identification of other places where things took place, or places mentioned
      - Who and where else is mentioned inside any double quotes - done by simple Stanford NLP NER
      - Where the sutta's events took place, and if present, the geographical name as it is spelled in the DPPN on Sutta Central.

- Lists (currently very spotty, will need to re-do) consisting of:
  - Comma-delimited lists
  - Sections of text repeated with a small change for each iteration
  - Causal sequences/chains or things described
  - Sections of text with lists between "..."

- dicts/:
  - location_variants.json: a lookup for all location variants to their dictionary base name as per in the SuttaCentral version of the DPPN,


- data/initial_geographic_locations.json: A single dictionary with the geographic coordinates, location text from sutta, and the SC DPPN headword for all suttas in the 4 Nikayas. Primary key between coodinates and location text is the dppn headword which is worked out from first proper name in the location values from data/speakers_locations/

Known issues:
 - Identification of people spoken about within quotes is handled by untrained Named-Entity Recognition currently using Stanford NLP (stanza) which can miss things not capitalised and mix up locations and people sometimes.
  - Incorrect attributions are still present.

Snp, Thig, Thag, others likely forthcoming.

Actual python code forthcoming.
