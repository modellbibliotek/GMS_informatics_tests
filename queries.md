# Exempelqueries
Användningsfall nämnda av medverkande i https://genomicmedicine.se/
 
## Forskning

### Sekvensdata
* Ge mig provnamnen på alla data där patienten har diagnos X och där proverna är Illumina WGS och där rådatat finns i fastq-format.
* Ge mig provnamnen på alla data där patienten har cancer av typ X, där patienten har metastaser (Stage IV), där det finns prov från både initial tumör och uppföljning, och där det finns tumör-normal par.
 
### Variant
* Ge mig provnamnen på alla data där patienten har variant M och som får användas för forskning.
 
## Klinik
### Sekvensdata
* Ge mig information om all tidigare sekvensdata som finns listad för patient Z, plus remiss för varje sekvensdata.
 
### Variant
* Ge mig diagnoserna och remitterande läkare på alla patienter som har variant Y markerad som kausal variant.
* Ge mig alla annoteringar på variant Y som finns registrerade, och information om kvalité och läsdjup.

## Tidigare nämnda variant-databas-frågor
Definiera vad man behöver söka på. Info på vad man vill kunna söka fram mellan sjukhus:
Har denna variant hittats hos något annat sjukhus? Hur hanterades varianten hos sjukhuset?

* Ge mig alla personnummer där personer hade den här diagnosen.
* Hur många utbrott fanns av den här stammen under 2000.

För att söka fram data är tanken att använda HCI, för indexering. Exempelvis kanske man vill söka på en enskild variant och få tillbaka alla dokument där den förekommer. SQL används när någon vill ställa querys via HCI.

## AQL
Exempel på frågor beskrivna med openEHRs frågespråk AQL (Archetype Query Language)
* Lite lästips om AQL:
   * Själva specifikationen för AQL är kanske lite torr, men uttömmande: https://specifications.openehr.org/releases/QUERY/Release-1.1.0/AQL.html#_overview 
   * AQL-Exempel kan vara roligare att läsa https://specifications.openehr.org/releases/QUERY/Release-1.1.0/AQL_examples.html
   * När man sedan kör fast eller blir förvirrad av hur AQL-svaren beter sig så kan det vara intressant att läsa https://serefarikan.com/2021/06/19/archetype-query-language-the-confusing-bits/ skrivet av Seref som doktorerat i ämnet…

### 1.
