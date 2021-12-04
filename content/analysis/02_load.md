---
Title: Laddningstider
Description: This is an analysis of loading times
Template: analysis
---
Laddningstider
=======================

Jag valde samma sidor för detta som för färg-analysen.
- Sweclockers
  <img src="%base_url%/image/sweclockers.png">
- Feber
  <img src="%base_url%/image/feber.png">
- Omni
  <img src="%base_url%/image/omni.png">

Metod
-----------------------
Jag gick in på sidan med 2 webläsare, först med chrome canary då jag inte har några addons där.
Mätte sidan 3 ggr och laddade om med shift-cmd-r, noterade ner resultaten.
Sen märkte jag att i firefox, även om det var ett privat fönster laddades inga annonser.
Jag gjorde samma mätning där och noterade ner snittet.

Resultat
-----------------------

### Sweclockers
Sidan var ganska snabb på att ladda. snittet låg på 1.95s med adds å 0.8s utan annonser.
När annonserna var på låg det på 6mb totalt att hämta men man hämtade strax över hälften.
Utan annonser var sidan bara på 2.4mb vilket är en markant skillnad. Det märks
att annonser är större delen av vad som laddas vilket är riktigt kass.

Den får förhållandevis högt betyg av pagespeed på 88 för desktop men riktigt usel på mobil.
Orsaken till sämre betyg verkar vara att den de inte lagrar "next-gen" format av bilderna utan 
ganska oeffektiva bilder, där finns mycket förbättring, iaf för mobila sidan där det
har större påverkan.

### Feber
Denna sidan är väldigt reklamfinansierad och det märks.
Den laddar fort utan reklam på snitt ca 2s. men då är sidan på 6mb och man
tankar hem ca 2mb.
När man däremot inte har reklam verkar sidan stanna eller något i väntan på response
från klienten om reklamen (en teori bara) och laddningstiden på sidan
ökar till ca 5s. Smått irriterande.
Tror de undersöker om man har ad-blocker eller liknande (jag körde utan och blockerade på dns-nivå vilket sidorna inte märker.)

Deras pagespeed-betyg är sämre men det de klagar på där är att de har javascript
som inte används.
För mobil är det samma men även att de ska hantera bilder utanför bild samt storleken på bilderna bättre.

### Omni
Omnis sida laddar ungafär lika fort med och utan annonser.
Storleken på sidan går dock från 8.8mb ner till ca 3mb om man
inte laddar annonserna.
Man tar även bara hem 1.43s ist för 3.4mb vilket är viktigt när man har mobil.

Pagespeed gav den sämre betyg än swec men de klagade mest på att bilderna hade fel storlek.
På mobila sidan var det främst samma som för swec, att de skulle använda ett mer effektivt bildformat.

Analys
-----------------------
Det vanligaste felet verkar vara relaterat till bilder och att 
man använder ett oeffektivt format på bilderna, som inte kan komprimeras bra för 
sämre enheter som mobiler etc smidigt.
Man har istället bilder i deras glory och enheten får hantera det.
Det kan ha att göra med att hastigheterna på mobilt nät och mobiler är såpass
hög nu att det inte nödvändigtvis spelar jättestor roll eg.
Men det är ju alltid bra att optimera så mycket det går men det handlar nog om prioriteringar.

En sak är dock säker, sidor är mycket bättre på alla sätt utan all sablans
reklam. Feber verkar ju ha kontroller för att se massa saker om du har adblocker eller liknande.
De har funktioner som gör att om du har adblocker och de märker det får du inte
möjligheten att ha oändlig scroll samt att de påpekar att du blockar skiten 
med jämna mellanrum. Tacka techguden för dns-block.

Resultat
-----------------------
Rangordningen av dessa enligt pagespeed är:
Sweclockers
Omni
Feber

För mobil är det ungefär samma fast omni och Swec får lika dåligt betyg, om än
bättre än feber.

Min rangordning är dock:
Omni
Sweclockers
Feber.

Motivering:
Omni går lika fort oavsett om du visar annonser eller inte, vilket
tyder på att större delen av deras sida inte är aids (läs reklam).
Swec kommer därefter då de har mycket annonser men de gör inte samma skit som feber
där de blockerar funktioner om du blockerar annonser.
Febers webmasters kan gå å dra något gammalt över sig.

Har ingen specifik gräns för när jag upplever en sida långsam men 
om man går på resultaten så hänger det lite på hur sidan 
fungerar, om den visar allt först när den är klar eller om den
fokuserar på det som visas först, då kan det ta fler sekunder
att ladda sidan men sålänge det absolut viktigaste 
så kommer resten laddas klart innan man kommer till det.
Men skulle säga att 1-2s är acceptabelt, beroende på 
adblocks och addons som ghostery som ska blocka massa skit.
Mer än så då börjar man tänka att något är långsamt.

Jag tycker Swec och Omni känns snabba om man stoppar annonser.
Annars är endast omni ok.
Feber känns snabb med annonser men så oerhört bloated att man inte vet vad man heter.

Det är endast jag som gjort denna analys.