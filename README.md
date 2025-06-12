# Reuma_2.0
Reuma casus Transcriptomics

## Inleiding
De auto-immuunziekte reuma, oftewel reumatoïde artritis (RA), is een chronische ontstekingsreactie waarbij het afweersysteem de eigen gewrichten aanvalt. Dit leidt tot pijn, zwelling en stijfheid, vaak aan beide kanten van het lichaam wat op den duur schade kan veroorzaken aan het kraakbeen, bot en andere weefsels. Naast gewrichten kunnen ook organen zoals de longen of het hart beschadigd raken. Verhoogde niveaus van TNF- α en IL-6, twee cytokines die vooral opspelen tijdens ontstekingsreacties, kunnen bij onderzoek een indicatie zijn van reuma in een patiënt. Zonder behandeling kan RA leiden tot blijvende beperkingen en een kortere levensverwachting. (Díaz-González & Hernández-Hernández, 2023)

Een geneesmiddel is nog niet gevonden, maar klachten worden vaak onderdrukt met anti-reumatische middelen zoals methotrexaat (MTX) wat de proliferatie van RA-gerelateerde ontstekingscellen remt via het folaatantagonismepad. MTX werkt een ontstekingsremmende werking uit op verschillende pathways, zoals het adenosine-signaalpad. (Zhao et al., 2022) 

In dit onderzoek wordt onderzocht welke genen tot expressie komen bij mensen met RA en welke metabolic pathways (metabole routes) daarbij veranderen.

## Methode
200 woorden
Voor dit onderzoek is RNA van mensen met en zonder reuma onderzocht om te kijken welke genen anders werken bij reuma. Eerst is met de Rsubread-package een index gemaakt van het menselijk DNA en zijn de RNA-lezingen (FASTQ-bestanden) gekoppeld aan dit DNA met align(). Daarna zijn met featureCounts() per gen het aantal RNA-stukjes geteld.
De tellingen zijn geanalyseerd met DESeq2 om te zien welke genen meer of minder actief zijn bij reuma. Er is gekeken naar genen met een p-waarde kleiner dan 0.05 en een log2FoldChange groter dan 2 of kleiner dan -2. Met goseq en GO.db is onderzocht welke biologische processen bij deze genen horen. De top 10 processen zijn gevisualiseerd met ggplot2. Met EnhancedVolcano is een vulkaanplot gemaakt die laat zien welke genen het meest verschillen tussen reuma en gezond. Tot slot is met pathview gekeken naar het reuma-pad in KEGG (hsa05323), waarbij verschillende kleuren laten zien welke genen verhoogd of verlaagd zijn.

## Resultaten
200 woorden


## Conclusie
200 woorden


## Referenties
PDF bestand
