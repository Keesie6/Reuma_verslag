# Reuma_2.0
Reuma casus Transcriptomics

## Inleiding
De auto-immuunziekte reuma, oftewel reumatoïde artritis (RA), is een chronische ontstekingsreactie waarbij het afweersysteem de eigen gewrichten aanvalt. Dit leidt tot pijn, zwelling en stijfheid, vaak aan beide kanten van het lichaam wat op den duur schade kan veroorzaken aan het kraakbeen, bot en andere weefsels. Daarnaast kunnen cardiovasculaire aandoeningen versneld ontwikkelen zoals hartfalen, reumatoïde noduli en pericarditis. RA gepaard met een cardiovasculaire ziekte zorgt voor een hoge morbiditeit. (Sanghavi et al., 2022)
Verhoogde niveaus van TNF- α en IL-6, twee cytokines die vooral opspelen tijdens ontstekingsreacties, kunnen bij onderzoek een indicatie zijn van reuma in een patiënt. Zonder behandeling kan RA leiden tot blijvende beperkingen en een kortere levensverwachting. (Díaz-González & Hernández-Hernández, 2023)

Een geneesmiddel is nog niet gevonden, maar klachten worden vaak onderdrukt met anti-reumatische middelen zoals methotrexaat (MTX) wat de proliferatie van RA-gerelateerde ontstekingscellen remt via het folaatantagonismepad. MTX werkt een ontstekingsremmende werking uit op verschillende pathways, zoals het adenosine-signaalpad. (Zhao et al., 2022) 

In dit onderzoek wordt onderzocht welke genen tot expressie komen bij mensen met RA en welke metabolic pathways (metabole routes) daarbij veranderen.

## Methode
200 woorden
Voor dit onderzoek is RNA van mensen met en zonder reuma onderzocht waarbij is gekeken naar de genexpressie bij vier mensen met reuma en vier mensen zonder reuma (controle). 
Eerst is met de Rsubread-package (versie 2.20.0) een index gemaakt van het menselijk DNA en zijn de RNA-lezingen (FASTQ-bestanden) gekoppeld aan dit DNA met align(). Daarna zijn met featureCounts() per gen het aantal RNA-stukjes geteld. De tellingen zijn geanalyseerd met DESeq2 (versie 1.46.0) om te zien welke genen meer of minder actief zijn bij reuma. Er is gekeken naar genen met een p-waarde kleiner dan 0.05 en een log2FoldChange groter dan 2 of kleiner dan -2. Met goseq (versie 1.58.0) en GO.db (versie 3.20.0) is onderzocht welke biologische processen bij deze genen horen. De top 10 processen zijn gevisualiseerd met ggplot2 (versie 3.5.2). Met EnhancedVolcano (versie 1.24.0) is een vulkaanplot gemaakt die laat zien welke genen het meest verschillen tussen reuma en gezond. Tot slot is met pathview (versie 1.46.0) gekeken naar het reuma-pad in KEGG (hsa05323) (versie 1.46.0), waarbij verschillende kleuren laten zien welke genen verhoogd of verlaagd zijn.

## Resultaten
200 woorden


## Conclusie
200 woorden


## Referenties
PDF bestand
