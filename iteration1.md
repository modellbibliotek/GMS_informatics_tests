# Iteration 1: very simplified (and not quite realistic) use of models

In this first iteration of experiments several process steps are lumped together in a few templates
mostly intended as simplified scaffolds to show some of the detailing possibilities. 

Later iterations of experiments may divide the process in more realistic steps. Also, the phenopacket info should likely be kept in a separate more persistent part (folder?) of the EHR and updated by several clinicians/bioinformaticians instead of being put in a referral request...

## Test patients and identifiers in SFMI domain at ehrscape.com used in experiment

Role    | EHR ID                               | SubjectID* | Sex  | DOB | Requester order identifier | notes
--------| ------------------------------------ | ---------- | ---- | --- | -------------------------- | -----
**PROBAND** Child | ae2d4611-0a91-4c61-b2bc-ad81a648c0b5 |1448232|MALE |2011-04-01 |20210701-095 | several features and diagnosis
Sibling Child	|b23c290c-e411-40d9-bb91-8f38b8e6fe0d	|1448404|FEMALE	|2009-07-01 |20210701-095-a | 
Mother	|5aa91bcb-c20d-4f4a-a296-4a9e8a75972e	|1448356|FEMALE	|1985-03-01 |20210701-095-b | 
Father	|a02b734d-e027-4304-ba1b-92be06077c4c	|1448272|MALE	|1984-08-01 |20210701-095-c | Slender fingers

*) In iteration 1 the SubjectID is reused as phenopacket (person) identifier for simplicity but it should be replaced by a randomized identifier to improve anonymity in later experiment iterations 

Family ID = 123456

Test data for healthcare staff
https://docs.google.com/spreadsheets/d/1Av2tKe_unnk2um_XRVplAVyL47acJX7Y/edit#gid=153252209
Pattern for HSA ID in Region Östergötland: SE2321000040-TEST 


HSA-ID|Placerad under centrum	|Placerad under verksamhetsenhet	|Placerad under organisationsenhet	|Namn	|Personnummer	|Användarnamn	|Startdatum	|Slutdatum	|Legitimation	|HSA Yrkesroll |Titel	|Medicinsk titel	|Befattning AID	|Efternamn	|Mellannamn	|Tilltalsnamn	|Gruppförskrivarkod	|E-post
---|---|---|---|---|---|---|---|---|---|---|---|---|---|---|---|---|---|---
SE2321000040-4C1M |Primärvårdscentrum	|Vårdcentralen Tannefors |Gemensamt	|Erika Nilsson	|195002192382	|Lakare15	|2005-04-01	|	|Läkare	|Läkare	|distriktsläkare	|distriktsläkare	|201011	|Nilsson	| 	|Erika	|5922158	|Erika.Nilsson@test.lio.se

## Terminology

Example excerpts in https://docs.google.com/spreadsheets/d/1Ok2nROkn8sISQIY1OytF5MeDKZuZn7DtU3nGq8751_8/edit?usp=sharing

## Templates

### Referral request iteration 1
Contains the following archeteypes
```
openEHR-EHR-COMPOSITION.request.v1
openEHR-EHR-INSTRUCTION.service_request.v1
openEHR-EHR-ACTION.informed_consent.v0
openEHR-EHR-CLUSTER.pp_family_framework.v0
openEHR-EHR-CLUSTER.pp_pedigree.v0
openEHR-EHR-CLUSTER.pp_person.v0
openEHR-EHR-CLUSTER.pp_phenopacket_framework.v0
openEHR-EHR-CLUSTER.proband_or_relative_selection.v0 (locally created archetype)
```

## AQL Queries

List all patients with HPO Phenotypic feature = nnn and all phenopacket familiy IDs they are part of




## TODO:
Record structured info in form instead of PDF/paper (Possibly generate PDF afterwards.)

Sources to explore:
* http://www.analysportalen-labmedicin.skane.se/viewAnalys.asp?Nr=2776
* https://www.sahlgrenska.se/for-dig-som-ar/vardgivare/laboratoriemedicin/analyslistan/helexom/
* https://www.sahlgrenska.se/for-dig-som-ar/vardgivare/laboratoriemedicin/analyslistan/helgenom/

* Consent forms & extra patient info (GMS etc)

Digitize HPO phenotype selections from e.g. 
* Page 2 of http://analysportalen-labmedicin.skane.se/pics/Labmedicin/Verksamhetsomr%E5den/Klinisk%20genetik/Analysportalen/Remiss%20helgenomsekvensering%20(WGS)%20-%20konstitutionell%20utredning.pdf
* Checklista Klinisk genetik https://sahlgrenska-klinkem-analyser.vgregion.se/KGAP0173.pdf 

* Add a small archetype to Service Request extension slot to mark requst as beloning to a family investigation (trio etc) and include connecting proband id request - That can replace the current proband vs single archetype
