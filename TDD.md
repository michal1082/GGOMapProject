#  Custom Map
## Documentation

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
#### 1. Map library zonder API keys

**Gekozen optie:** Leaflet  

**Waarom:**  
Leaflet is volledig open-source, lichtgewicht en vereist geen API-keys. Hierdoor kan de map gemakkelijk op meerdere websites gebruikt worden zonder dat elke klant een apart account moet aanmaken.

**Alternatieven:**   
- **Google Maps JS API:** Zeer uitgebreid en bekend, maar vereist een API key en kan kosten met zich meebrengen bij veel gebruik.
- **Mapbox:** Makkelijk in gebruik, veel features en stijlen beschikbaar, maar vereist een API key en kan kosten met zich meebrengen bij veel gebruik.    

**Reden keuze:**  
Leaflet biedt de juiste balans tussen eenvoud, flexibiliteit en onafhankelijkheid van API keys waardoor er geen kosten zijn.

---

#### 2. Data van markers makkelijk aanpasbaar maken

**Gekozen optie:** Google Sheets als datasource  

**Waarom:**  
Google Sheets is eenvoudig te gebruiken door klanten, Het word makkelijk ingeladen door het systeem waar we in werken dat goed is voor de seo. Data zoals `image`, `name` en `description` kunnen makkelijk aangepast worden.

**Alternatieven:**  
- **JSON-bestanden op GitHub:** Makkelijk voor ontwikkelaars, maar minder intuïtief voor klanten.  
- **No-code databases zoals Airtable:** Ook mogelijk, maar vereist vaak een API key of account per klant.  

**Reden keuze:**  
Google Sheets is eenvoudig voor niet-technische gebruikers, schaalbaar zonder extra infrastructuur. En het word gebruikt voor goede SEO binnen ons systeem.

---

#### 3. Aanpasbaar land of regio op de kaart

**Gekozen optie:** GeoJSON bestanden op GitHub publiceren  

**Waarom:**  
GeoJSON is een standaardformaat voor geografische data. Door de bestanden openbaar op GitHub te zetten, kan Handlebars deze inlezen zonder dat er private database toegang nodig is. Hierdoor kan de klant het land of de regio eenvoudig aanpassen door een ander GeoJSON-bestand te selecteren.

**Alternatieven:**  
- **Shapefiles omzetten naar GeoJSON:** Goed voor uitgebreide geografische data, maar minder direct bewerkbaar.  
- **Direct vanuit een database server ophalen:** Kan krachtig zijn, maar vereist beheer van server en authenticatie, wat niet wenselijk is voor klanten zonder technische kennis.  

**Reden keuze:**  
GitHub + GeoJSON is eenvoudig, openbaar en direct compatible met Leaflet en andere JS map libraries.  

#### Belangrijke bronnen
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

