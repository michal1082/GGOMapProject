#  Custom Map
## Technical Design Document

---

## Omschrijving

### Wat?
een widget waarmee gebruikers een interactieve kaart kunnen aanpassen, inclusief het plaatsen van markers op specifieke locaties. Deze markers bevatten verschillende inhoudstypen, zoals afbeeldingen, tekst en knoppen, om gebruikers in staat te stellen gedetailleerde informatie over die locaties te presenteren. Bovendien moest de widget Street View-functionaliteit bieden en aanpasbaar zijn in termen van kleuren en marker inhoud.

### Doel?
Het belangrijkste doel was om bedrijven een eenvoudige manier te bieden om locaties aan te wijzen en informatie over die locaties te presenteren aan hun doelgroep.

### Hoe kom je op het idee?
Verzonnen door Jacques tijdens de meesterproef. 

### Doelgroep
bedrijven en organisaties die locatie gerelateerde informatie willen delen met hun klanten of doelgroep. Dit kan variëren van het markeren van fysieke winkels, kantoren of evenementenlocaties tot het tonen van specifieke interessante locaties voor toeristen of potentiële klanten.

### Voorbeelden

---

## Functionaliteiten

### Must 
- Als beheerder wil ik een LeafLet map kunnen gebruiken, omdat dit de basisfunctionaliteit van de kaart biedt.  
- Als beheerder wil ik een choropleth overlay kunnen toevoegen, omdat dit visuele gegevensweergave mogelijk maakt.  
- Als beheerder wil ik markers op de kaart kunnen plaatsen, omdat dit belangrijk is voor het tonen van specifieke locaties.  
- Als beheerder wil ik de inhoud van markers kunnen aanpassen met foto’s, tekst en knoppen, omdat dit de informatie die gebruikers ontvangen moet kunnen personaliseren.  
- Als beheerder wil ik de kaart kunnen verbinden met het systeem, omdat dit dynamische en actuele gegevensintegratie mogelijk maakt.  
- Als beheerder wil ik de achtergrond en de kaart aanpasbaar kunnen maken, omdat dit essentieel is voor de visuele afstemming op de behoeften van de gebruiker.  
- Bij elke marker kan je kiezen of je een adres hebt of niet. Als niet dan kun je lat, long coordinaten invoeren. in de sheets pakt de marker eerst het adres.

### Should
- Als beheerder wil ik de mogelijkheid hebben om street view in te zoomen, omdat dit de gebruikerservaring verbeterd door gedetailleerde weergaven van locaties mogelijk te maken.  
- Als beheerder wil ik het icoon van de marker kunnen aanpassen, omdat dit de herkenbaarheid en esthetiek van de kaart kan verbeteren.  
- Als beheerder wil ik de kleur van de kaartlijn kunnen aanpassen, omdat dit helpt bij het aanpassen van de visuele stijl van de kaart aan de behoeften van de gebruiker.

### Could
- Als beheerder wil ik de stijl van street view kunnen aanpassen, omdat dit extra mogelijkheden biedt voor het personaliseren van de gebruikerservaring.

### Won’t

---

## Realisatie

### Belangrijke keuzes
Het moet een map library zijn die geen API keys gebruikt zoals leaflet en geen mapbox zodat het op meerdere sites zonder verschillende accounts werkt.  

De data van de markers zoals image, name, description moeten makkelijk aanpasbaar zijn voor klanten dus het mag geen ingewikkelde database zijn zoals MySQL. Daarom wordt ervoor gekozen om de map te connecten met google sheets.  

Het land dat word getoont op de map moet aangepast kunnen worden door de klant. En handlebars kan geen private database accessen. Daarom worden geoJson map files op github public geupload en door die link opgehaald.  

### Belangrijke bronnen
- Map library: https://leafletjs.com/  
- Map style: https://www.openstreetmap.org/#map=7/52.154/5.295  
- Custom GeoJson: https://raw.githubusercontent.com/michal1082/StageExamen/main/custom.geo.json  

---

## Testplan

### Opstarten
**Test soort**  
Hoofdscenario  

**Scenario**  
Als bezoeker laad ik de widget in door op een pagina te gaan waar de widget op staat  

**Verwacht resultaat**  
De widget is volledig zichtbaar en in de console (F12) zijn geen aparte logs, warnings of error te zien.  

**Daadwerkelijk resultaat**  
zichtbaar zonder errors  

**Succes**  
Geslaagd  

---

### Tablet weergave
**Test soort**  
Hoofdscenario  

**Scenario**  
Als bezoeker bekijk ik de widget in de tabletweergave.  

**Verwacht resultaat**  
De widget ziet er alsnog goed uit, is leesbaar en wordt niet afgeknipt.  

**Daadwerkelijk resultaat**  
Werkt op tablet  

**Succes**  
Geslaagd  

---

### Mobiele weergave
**Test soort**  
Hoofdscenario  

**Scenario**  
Als bezoeker bekijk ik de widget op een mobiel.  

**Verwacht resultaat**  
De widget ziet er alsnog goed uit, is leesbaar en wordt niet afgeknipt.  

**Daadwerkelijk resultaat**  
Werkt op mobiel  

**Succes**  
Geslaagd  

---

### Markers zelfstandig toevoegen
**Test soort**  
Hoofdscenario  

**Scenario**  
Je klikt op marker toevoegen en vult de data in  

**Verwacht resultaat**  
de marker wordt weergeven op de kaart met de juiste data  

**Daadwerkelijk resultaat**  
Juiste data word getoont  

**Succes**  
Geslaagd  

---

### Markers toevoegen via sheets
**Test soort**  
Hoofdscenario  

**Scenario**  
Je connect de map met collecties  

**Verwacht resultaat**  
Alle markers worden weergeven op de map met de juiste data  

**Daadwerkelijk resultaat**  
connectie werkt en data wordt weergeven  

**Succes**  
Geslaagd  

---

### Inzoomen 
**Test soort**  
Hoofdscenario  

**Scenario**  
Je zoomt in op de map  

**Verwacht resultaat**  
De kleur van de map verandert in street view  

**Daadwerkelijk resultaat**  
street view werkt  

**Succes**  
Geslaagd  

