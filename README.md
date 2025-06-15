# Reuma_2.0
Auteur: Keshari Autar (5374308)
Klas: BM2B
Opleiding: Biologie en medisch laboratoriumonderzoek
Begeleider: Dewi van den Bergh
Datum: 20 - 06 - 2025

## Inleiding
De auto-immuunziekte reuma, oftewel reumatoïde artritis (RA), is een chronische ontstekingsreactie waarbij het afweersysteem de eigen gewrichten aanvalt. Dit leidt tot pijn, zwelling en stijfheid, vaak aan beide kanten van het lichaam wat op den duur schade kan veroorzaken aan het kraakbeen, bot en andere weefsels. Daarnaast kunnen cardiovasculaire aandoeningen versneld ontwikkelen zoals hartfalen, reumatoïde noduli en pericarditis. RA gepaard met een cardiovasculaire ziekte zorgt voor een hoge morbiditeit. (Sanghavi et al., 2022)
Verhoogde niveaus van TNF- α en IL-6, twee cytokines die vooral opspelen tijdens ontstekingsreacties, kunnen bij onderzoek een indicatie zijn van reuma in een patiënt. Zonder behandeling kan RA leiden tot blijvende beperkingen en een kortere levensverwachting. (Díaz-González & Hernández-Hernández, 2023)

Een geneesmiddel is nog niet gevonden, maar klachten worden vaak onderdrukt met anti-reumatische middelen zoals methotrexaat (MTX) wat de proliferatie van RA-gerelateerde ontstekingscellen remt via het folaatantagonismepad. MTX werkt een ontstekingsremmende werking uit op verschillende pathways, zoals het adenosine-signaalpad. (Zhao et al., 2022) 

In dit onderzoek wordt onderzocht welke genen tot expressie komen bij acht RNA-samples van mensen met en zonder RA en welke metabolic pathways (metabole routes) daarbij veranderen. Hierbij wordt gebruik gemaakt van Rstudio waar acht RNA-samples worden geanalyseerd met verschillende packages.

## Methode
Voor dit onderzoek is RNA van mensen met en zonder reuma onderzocht waarbij is gekeken naar de genexpressie bij vier mensen met reuma en vier mensen zonder reuma (controle). 
Eerst is met de Rsubread-package (versie 2.20.0) een index gemaakt van het menselijk DNA en zijn de RNA-lezingen (FASTQ-bestanden) gekoppeld aan dit DNA met align(). Daarna zijn met featureCounts() per gen het aantal RNA-stukjes geteld. De tellingen zijn geanalyseerd met DESeq2 (versie 1.46.0) om te zien welke genen meer of minder actief zijn bij reuma. Er is gekeken naar genen met een p-waarde kleiner dan 0.05 en een log2FoldChange groter dan 2 of kleiner dan -2. Met goseq (versie 1.58.0) en GO.db (versie 3.20.0) is onderzocht welke biologische processen bij deze genen horen. De top 10 processen zijn gevisualiseerd met ggplot2 (versie 3.5.2). Met EnhancedVolcano (versie 1.24.0) is een vulkaanplot gemaakt die laat zien welke genen het meest verschillen tussen reuma en gezond. Tot slot is met pathview (versie 1.46.0) gekeken naar het reuma-pad in KEGG (hsa05323) (versie 1.46.0), waarbij verschillende kleuren laten zien welke genen verhoogd of verlaagd zijn.

## Resultaten
In dit onderzoek is onderzocht welke genen tot expressie komen bij acht RNA-samples van mensen met en zonder RA en welke metabolic pathways (metabole routes) daarbij zijn veranderd. Hierbij is gebruik gemaakt van Rstudio en verschillende packages waarmee acht samples zijn geanalyseerd.!

Uit de RNA-seq analyse zijn in totaal 4572 genen geïdentificeerd die significant verschillend tot expressie komen tussen reumapatiënten en gezonde controles. Van deze genen vertonen 2085 een verhoogde expressie en 2487 een verlaagde expressie (padj < 0.05 en |log2FoldChange| > 1). In de volcano plot (Figuur 1) zijn deze genen zichtbaar, waarbij de spreiding tussen op- en neer-gereguleerde genen wordt weergegeven.

De GO-analyse laat zien dat een groot aantal van deze genen geassocieerd is met biologische processen. De top 10 meest significante GO-termen (Figuur 2) omvatten voornamelijk processen gerelateerd aan immuunrespons, cytokineactiviteit en ontstekingsreacties.

Daarnaast is met behulp van de KEGG pathway-analyse gekeken naar de betrokkenheid van genen binnen het “Rheumatoid arthritis” pathway (hsa05323). In Figuur 3 is te zien welke genen binnen deze pathway verhoogd of verlaagd tot expressie komen bij reuma, weergegeven in kleuren op basis van log2FoldChange-waarden.

## Conclusie
Op basis van de resultaten van dit onderzoek kan er worden vastgesteld dat er grote verschillen zijn in genexpressie tussen mensen met reuma (RA) en gezonde personen. 

In totaal zijn er meer dan 4500 genen gevonden die significant meer of minder actief zijn bij RA. Veel van deze genen zijn betrokken bij het afweersysteem en ontstekingsreacties. Uit de GO-analyse is gebleken dat er een aantal processen waaronder de immuunrespons en de cytokine-activiteit vaker voorkwamen bij de genexpressie van reuma patiënten. Dit wijst erop dat het immuunsysteem op een andere manier werkt dan bij gezonde mensen. 

Daarnaast liet de KEGG-analyse zien dat het RA-pathway (hsa05323) genen bevatte die verschillend tot expressie komen bij patiënten met reuma. Deze genen kunnen dus potentieel betrokken zijn bij het ziekteproces en dragen mogelijk bij aan reumatische klachten en ontstekingen veroorzaakt door reuma. 

Concluderend, RA is een ontstekingsziekte is op moleculair niveau waarbij het eigen afweersysteem een grote rol speelt. Deze resultaten geven meer inzicht in hoe RA werkt en kunnen in de toekomst helpen bij het vinden van nieuwe medicijnen of biomarkers.

## Referenties
PDF bestand
