# suttamap
Buddhist Sutta metadata produced in a boring way by code, with much help from other code, LLMs, eyes and muscles.

All of these need to be checked rigorously before being treated as absolutely correct (it will not be correct). Data structures may change. Once everything is double-checked 100%, the warnings will be removed from the _comment keys in json files.

Inside the data/ folder is for Digha Nikaya, Majhima Nikaya, Samyutta Nikaya and Anguttara Nikaya, Dhammapada, Suttanipata, Itivuttaka, Therigatha, Theragata, Udana, Bhikkhunī Vibhaṅga and Pātimokkha, Bhikkhu Vibhaṅga and Pātimokkha:
  - speakers/ Identification of speakers of anything in double-quotes in data/speakers single segment per speaker of each matching bilara's format. 
  - people_locations_source_data: speech expressed as ranges, as well as:
      - Identification of other people present or mentioned
      - Identification of other places where things took place, or places mentioned by people
      - Who and where else is mentioned inside any double quotes - done by simple Stanford NLP NER
      - Where the sutta's events took place, and if present, the geographical name as it is spelled in the DPPN on Sutta Central.

- Lists (currently very spotty, will need to re-do or use different models on the basis of what needs to be more explicit - the lists are currently strange) consisting of:
  - Comma-delimited lists
  - Sections of text repeated with a small change for each iteration
  - Causal sequences/chains or things described that might be considered happening one after the other
  - Sections of text with lists between "..." in Bhante Sujato's translations - peyalas.

- dicts/:
  - location_variants.json: a lookup for all location variants to their dictionary base name as per in the SuttaCentral version of the DPPN. Something similar will need to be made for DPPN to point to things in data/suttas_per_person_words_spoken.json.

- data/initial_geographic_locations.json: A single dictionary with the geographic coordinates, location text from sutta, and the SC DPPN headword for all suttas in  Digha Nikaya, Majhima Nikaya, Saṃyutta Nikaya and Anguttara Nikaya, Dhammapada, Sutta Nipata, Itivuttaka, Therigatha, Theragata, Udana, Bhikkhunī Vibhaṅga and Pātimokkha, Bhikkhu Vibhaṅga and Pātimokkha. Primary key between coodinates and location text is the DPPN headword which is worked out from first proper name in the location values from data/people_locations_source_data/ .
- data/suttas_per_person_words_spoken.json: A single dictionary indexed by speakers, with the speaker's suttas sorted by count of words spoken. Sorted secondarily by mentions.
- data/persons_per_sutta_words_spoken.json: A single dictionary indexed by suttas, with the sutta's speakers sorted by count of words spoken. Sorted secondarily by mentions.

Known issues:
- Identification of people spoken about within quotes is handled by untrained Named-Entity Recognition currently using Stanford NLP (stanza) which can miss things not capitalised and mix up locations and people sometimes.
- Incorrect attributions are still present.
- Any time the Buddha is not named as the speaker in the sutta itself, he is listed as "the Buddha (assumed)". This is likely to be removed for all scriptures that are generally accepted to be the words of the Buddha without being explicitly mentioned as so.
- Speakers are gradually being de-duplicated by changing the names to be the same in people_locations_source_data/ .
- Mentions are not exact (sometimes mentions will be more than the actual amount in the sutta, double-counting sometimes, but consistently so)
- Presence is sometimes mis-determined if speakers are speaking figuratively or generally might be read as though they were being addressed here and now.

Vinaya books pvr and kd forthcoming.

Actual python code forthcoming.

Quotations inside quotations (and inside those quotations) forthcoming. At the moment speakers is only words inside double quotes.

Per-sutta and per-person dictionaries with only those mentioned in the DPPN fortchcoming.