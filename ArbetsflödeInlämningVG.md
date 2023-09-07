# Arbetsflöde för AI-projekt med linjär regression

## Syfte

Överblick över de vanliga stegen i arbetsflödet för att skapa en maskininlärningsapplikation. Rapporten fokuserar på scenariot att förutspå huspriser baserat på olika egenskaper, såsom antalet rum, geografiska läget och storleken på huset.

## Datainsamling

Det första steget i ett maskininlärnings- eller djupinlärningsprojekt är att samla in data. I detta scenario kan datan samlas in från olika källor, förslagsvis:

* Fastighetsmäklare
* Lantmäteriet
* Annan publik källa

Datan kan lagras i olika format, såsom CSV, JSON eller i en SQL-databas. Det är viktigt att välja ett format som är lätt att arbeta med för de kommande stegen i arbetsflödet. Datan kan sparas lokalt eller i molnet, t.ex. erbjuder Amazon, Google och Microsoft molnlagringstjänster kopplade till maskininlärning.

## Datavisualisering

När datan har samlats in är det lämpligt att visualisera den för att få en bättre förståelse för dess innebörd. Detta kan i Python göras med hjälp av olika verktyg, såsom MatPlotLib, Pandas eller Seaborn.

Datavisualisering kan hjälpa till att identifiera trender, mönster och s.k. outliers i datan. Detta kan vara till hjälp i de kommande stegen i arbetsflödet.

## Databeredning

Databeredning eller preprocessing är det steg där datan förbereds för modellering. Detta kan innebära att man tar bort felaktiga eller ofullständiga data, att man normaliserar datan (designar databasens struktur för att lagra data på ett logiskt sätt, där man minskar redundans och beroenden mellan tabeller) och att man konverterar datan till det format modellen kräver. Man kan även rensa ut orepresentativa outliers, som kan ha uppstått på grund av t.ex. mätfel, där det linjära sambandet mellan variablerna inte är så tydligt, och som därför kan försämra modellen.

Datan kan vara av tre typer:

1. *Numerisk* - t.ex ålder eller inkomst
2. *Kategorisk* - t.ex. nationalitet, färg
3. *Kategorier på en skala* - t.ex. låg, medium, hög

Det är viktigt att datan efter preprocessing är ren och konsekvent för att modellen sedan ska kunna lära sig korrekt. Förbehandling av data är kanske det viktigaste steget i maskininlärning. Det finns de som anser att 80% av tiden bör läggas på preprocessing, och 20% på det som kommer därefter.

## Träning

Innan man tränar sin modell måste man välja modell, efter vad man antar kommer att bli en så bra modell som möjligt för uppgiften.
När man tränar en modell delar man upp sina data i tre delar:

1. Träningsdata
2. Valideringsdata
3. Testdata

Träningsdatan används för att träna modellen, valideringsdatan för att finjustera, och testdatan för att utvärdera.

Det finns tre olika övergripande tekniker för maskininlärning:

* *Supervised learning* - där man matar etiketterad data till en algoritm med ett förväntat resultat.
* *Unsupervised learning* - en algoritm matas med oetiketterad data.
* *Reinforcement learning* - belönar bra beteende och straffar dåligt. 

Träningen inom maskininlärning sker med hjälp av algoritmer, där träningsdatan används för att lära en klassificerare att sätta datan i rätt fack eller förutspå ett värde.

I detta exempel använder vi linjär regression ( *supervised learning*).

### Linjär regression

Linjär regression är en enkel men kraftfull algoritm som kan användas för att förutspå ett kontinuerligt värde, såsom huspriser eller försäljningsvolymer. Det finns även andra regressionsmodeller som kan användas för att modellera kontinuerliga (numerära) värden.

Modellen antar att relationen mellan en beroende variabel $y$ och ett antal oberoende variabler är linjär. Algoritmen bygger därmed på en linjär ekvation som beskriver hur ett prediktionsvärde, i detta fall huspriset, relaterar till ett antal egenskaper eller förklarande variabler, till exempel antalet rum, det geografiska läget och storleken på huset.

Den linjära regressionsmodellen kan alltså användas för att göra förutsägelser om den beroende variabeln för nya värden på de oberoende variablerna.

I linjär regression försöker man minimera felet mellan de observerade datapunkterna och regressionslinjen. Detta kallas för minstakvadratmetoden.

Man skiljer mellan enkel linjär regression, där man bara har en oberoende variabel, och multipel linjär regression, där man kan ha ett godtyckligt antal. I detta exempel handlar det om multipel linjär regression, då det är ett antal olika parametrar som påverkar huspriset.

## Modellutvärdering

När modellen har tränats är det viktigt att utvärdera dess prestanda. Detta görs lämpligtvis genom att använda det testset av data som sparats undan, och som inte använts för att träna modellen.

Det finns ett antal olika mått som kan användas för att utvärdera en modells prestanda, såsom R-squared, root mean squared error (RMSE) som är det som oftast används när det handlar om regression, och mean absolute error (MAE).

Innan driftsättning kan man med fördel utvärdera ett antal olika modeller för att se vilken som presterar bäst.

## Driftsättning

När modellen har utvärderats och godkänts är den redo att driftsättas. Detta innebär att modellen görs tillgänglig för att användas av användare eller inom ett företag/organisation.

Driftsättning kan göras på olika sätt, såsom att publicera modellen som en API eller att integrera den i en webbapp.

När man driftsatt modellen är det ofta lämpligt att regelbundet utvärdera och uppdatera modellen.

Olika sätt att förbättra modellen och produkten på efter driftsättning är:

- A/B-testning: Jämför prestandan hos den befintliga processen och systemet med den nuvarande modellen. Man kan förbättra modellens prestanda baserat på resultatet.
- Utförlig dokumentation: Bra dokumentation är till stor hjälp för alla verktyg eller tjänster. Hur man använder din modell, vilka resultat du kan förvänta dig och var du kan komma åt dem är några av dem.

## Teknologier

Det finns ett antal olika teknologier som kan användas i de olika stegen i maskininlärningsprocessen. Några vanliga teknologier är:

- SQL för att lagra data i databaser
- Pandas för att arbeta med data
- Scikit-learn för maskininlärning
- Matplotlib eller Plotly för visualisering
- TensorFlow för djupinlärning
- Azure ML för att arbeta i molnet

## Källhänvisningar

* [Linjär regression - Wiki](https://en.wikipedia.org/wiki/Linear_regression)
* [Maskininlärning - Wiki](https://en.wikipedia.org/wiki/Machine_learning)
* [Resurser v.36](https://github.com/everyloop/AI-intro-AI23/blob/main/Resources/week3.md)
* [Workflow of a machine learning project](https://towardsdatascience.com/workflow-of-a-machine-learning-project-ec1dba419b94)
* [Machine Learning Workflow - A Complete Guide](https://blog.nimblebox.ai/machine-learning-workflow)
* *Hands-On Machine Learning with Scikit-Learn, Keras, and TensorFlow Concepts, Tools, and Techniques to Build Intelligent Systems*, Aurélien Géron (2022), kap 1-2.