# Genexpressieanalyse van reumatoïde arthritis: inzicht in immuunprocessen en potentiële biomarkers

<p align="center">
  <img src="Referenties/Reuma plaatje.png" alt="Reuma" width="550" />
</p>

Auteur: Keshari Autar (5374308)
  |  Klas: BM2B
  |  Opleiding: Biologie en medisch laboratoriumonderzoek
  |  Begeleider: Dewi van den Bergh
  |  Datum: 21 - 06 - 2025

## Inleiding
De auto-immuunziekte reumatoïde artritis (RA) is een chronische ontstekingsreactie waarbij het afweersysteem de eigen gewrichten aanvalt. Naast klachten als pijn, zwelling en stijfheid kan het ook schade brengen aan andere lichaamsweefsels. Cardiovasculaire aandoeningen kunnen  versneld ontwikkelen zoals hartfalen en reumatoïde noduli wat zorgt voor een hoge morbiditeit (Sanghavi et al., 2022). Verhoogde niveaus van cytokines als TNF- α en IL-6 kunnen bij onderzoek een indicatie zijn van reuma in een patiënt (Díaz-González & Hernández-Hernández, 2023). Klachten worden vaak onderdrukt met anti-reumatische middelen zoals methotrexaat (MTX) wat de proliferatie van RA-gerelateerde ontstekingscellen remt via het folaatantagonismepad (Zhao et al., 2022). Reuma heeft een genetische basis, maar leefstijl en roken kunnen het ziekteproces versnellen. Hoewel er een aantal behandeltherapiëen beschikbaar zijn, reageren nog veel patiënten niet goed op de behandeling (Smolen et al., 2016). 

In dit onderzoek wordt onderzocht welke genen tot expressie komen bij acht RNA-samples van mensen met en zonder RA en welke metabolic pathways (metabole routes) daarbij veranderen. De samples worden vergeleken met het humane genoom in R met behulp van verschillende packages waarbij wordt gekeken naar de genexpressie, de verschillende processen waarbij deze genen een rol spelen en welke metabolix pathways een verhoogde of verlaagde expressie vertonen.

## Methode
Eerst is met de Rsubread-package (versie 2.20.0) een index gemaakt van het [humane genoom](https://github.com/Keesie6/Reuma_2.0/blob/main/R/Humane%20genoom) en zijn de acht [RNA FASTQ-bestanden](https://github.com/Keesie6/Reuma_2.0/blob/main/R/Data_RA_raw.zip) gekoppeld aan dit DNA met align(). Daarna zijn met de [count matrix](https://github.com/Keesie6/Reuma_2.0/blob/main/R/count_matrix.txt) en featureCounts() per gen het aantal RNA-stukjes geteld. De tellingen zijn geanalyseerd met DESeq2 (versie 1.46.0) om te zien welke genen meer of minder actief zijn bij reuma. Er is gekeken naar genen met een p-waarde kleiner dan 0.05 en een log2FoldChange groter dan 2 of kleiner dan -2. Met goseq (versie 1.58.0) en GO.db (versie 3.20.0) is onderzocht welke biologische processen bij deze genen horen. De top 10 processen zijn gevisualiseerd met ggplot2 (versie 3.5.2). Met EnhancedVolcano (versie 1.24.0) is een vulkaanplot gemaakt die laat zien welke genen het meest verschillen tussen reuma en gezond. Tot slot is met pathview (versie 1.46.0) gekeken naar het reuma-pad in KEGGREST (hsa05323) (versie 1.46.0), waarbij verschillende kleuren laten zien welke genen verhoogd of verlaagd zijn. Het [R-script](https://github.com/Keesie6/Reuma_2.0/blob/main/R/Rscript) en het [flowschema](https://github.com/Keesie6/Reuma_2.0/blob/main/Data/Flowschema.png) voor een overzichtelijke weergave van de methode staan in een apart mapje.

## Resultaten
Uit de RNA-seq analyse werden in totaal 4572 genen geïdentificeerd die significant verschillend genexpressie vertoonden tussen reumapatiënten en gezonde samples. De genexpressie weergegeven in de [vulkaanplot](https://github.com/Keesie6/Reuma_2.0/blob/main/Data/Volcano%20plot.png) lieten de niet-significante genen (grijs) zien, genen alleen log2FC > 2 of < -2 (groen) en genen met log2FC en de p <0.05 (rood). 

De [GO-analyse](https://github.com/Keesie6/Reuma_2.0/blob/main/Data/Enriched%20Go%20Terms.png) gaf een top 10 Enriched GO-termen welke betrokken waren bij bepaalde processen in het lichaam waarbij veel genen vooral te maken hadden met de afweerreactie, cytokines en ontstekingen. 

De [KEGG pathway-analyse](https://github.com/Keesie6/Reuma_2.0/blob/main/Data/hsa05323.pathview.png) liet zien welke genen in de Rheumatoid Arthritis pathway verhoogd (rood) of verlaagd (groen) tot expressie kwamen op basis van log2FoldChange-waarden.  
De BAFF receptor, ofwel BLYS receptor, wordt gecodeerd door het gen TNFRSF13C en draagt samen met de cytokine APRIL bij aan de overleving en proliferatie van B-cellen. (Smulski & Eibel, 2018). Anti-citrullinated protein antibodies (APCA) zijn specifieke antilichamen tegen gecitrullineerde eiwitten en fungeren als vroegtijdige biomarker voor ernstige RA (Tsaltskan & Firestein, 2022). Een ontstekingsreactie stimuleert B-cellen tot de aanmaak van APCA’s zoals IgG wat in het blauw omcirkeld staat als [toll like signaling pathway](https://github.com/Keesie6/Reuma_2.0/blob/main/Data/hsa05323.pathview%20Bcell.png) (Smulski & Eibel, 2018).

## Conclusie
Op basis van de resultaten van dit onderzoek kan er worden vastgesteld dat er grote verschillen zijn in genexpressie tussen mensen met reuma (RA) en gezonde personen. Er zijn 4572 genen gevonden die significant meer of minder actief zijn bij RA waarvan veel betrokken zijn bij het afweersysteem en ontstekingsreacties. Dit wijst erop dat het immuunsysteem op een andere manier werkt dan bij gezonde mensen. 

Daarnaast liet de KEGG pathway-analyse zien dat het RA-pathway (hsa05323) genen bevatte die verschillend tot expressie komen bij patiënten met reuma zoals  de toll like signaling pathway. Dit wijst erop dat deze genen mogelijk betrokken zijn bij RA. Als vervolgonderzoek kan onderzocht worden of eiwitten zoals BLYS en APCA’s biomarkers zijn voor RA, door genexpressie en eiwitniveaus in bloed van patiënten en controles te meten (RT-qPCR/ELISA) en deze te koppelen aan ziekteverloop en klachten.

## Referenties
![Referenties](https://github.com/Keesie6/Reuma_2.0/blob/main/Referenties/Referenties%20Reuma%201.pdf)

## Data Stewardship
[Beheren](https://github.com/Keesie6/Reuma_2.0/blob/main/Datastewardship/Beheren) en 
[GitHub](https://github.com/Keesie6/Reuma_2.0/blob/main/Datastewardship/GitHub)
