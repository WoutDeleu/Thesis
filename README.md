# Thesis - KU Leuven, Wout Deleu, 2023

Welcome to my Thesis Text repository! Here, you'll find the complete text of my thesis work, available for reference and exploration. 🎓✍️

Feel free to dive in and explore the contents. If you have any questions or comments, don't hesitate to reach out. Happy reading and researching! 🤓📖💡

## Time Is Running Out

### Assessing Temporal Privacy of Privacy Zones in Fitness Tracking Social Networks

In een maatschappij waar sociale media alomtegenwoordig is, zijn de
privacybezorgdheden hierrond evenzeer erg actueel. Bij het ontwikkelen van
applicaties moeten privacywetgevingen en -bezorgdheden in acht genomen worden.
Dit neemt echter niet weg dat in heel wat applicaties nog gebreken te vinden
zijn in de uitvoering van het privacybeleid. In deze scriptie wordt de focus
gelegd op de uitvoering van het beleid binnen de fitnesstrackers. Dit zijn
platformen met als doel gegevens (die betrekking hebben op sportactiviteiten)
op te slaan en te delen met andere gebruikers. Dit zijn gegevens zoals
hartslag, gps-locaties, etc. Sommige van deze gegevens kunnen mogelijk
gevoelige informatie bevatten of vrijgeven. Gedurende deze thesis wordt
getracht om deze mogelijk gevoelige informatie uit te buiten, met de nadruk op
gps-gerelateerde data. Het grootste gevaar bij het delen van deze locaties is
het vrijgeven van locaties die je liever niet deelt met de buitenwereld, zoals
bv.\ een woonplaats.

Heel wat van deze fitnesstrackers zijn zich bewust van de mogelijke gevaren en
gaan op gelijkaardige manieren te werk om de privacy van de gebruiker te
garanderen. Dit gaat echter ten koste van gebruiksvriendelijkheid. Vanuit het
perspectief van ontwikkelaars wordt de trade-off tussen privacy en
gebruiksvriendelijkheid constant gemaakt. Op de meeste platformen zoals Strava
en Garmin worden gelijkaardige privacy features geïmplementeerd. Bijvoorbeeld
het verbergen van activiteiten voor andere gebruikers, of enkel activiteiten
weergeven voor je volgers. Maar een ander veelgebruikte techniek is gekend als
het implementeren van \textit{EPZ's} (Endpoint Privacy Zones). Een \textit{EPZ}
is een cirkel, of bij uitzondering een polygoon, opgezet rond een gevoelige
locatie. Deze cirkels worden opgesteld met een radius gekozen door de
gebruiker. Het centrum van de EPZ zal een willekeurig punt zijn in de buurt van
de locatie in kwestie. Deze kan niet verder dan 70\% van de radius verwijderd
zijn van de gevoelige locatie in het geval van Strava. Elk stuk van het
afgelegde traject dat binnen deze zone ligt zal worden verborgen voor de andere
gebruikers.

Het verbergen van delen van de route is echter geen waterdichte implementatie,
want hierbij worden bijhorende gegevens niet aangepast of mee verborgen.
Bijvoorbeeld wordt de totale afgelegde afstand van een activiteit niet
aangepast. Voorafgaand onderzoek toonde aan dat het mogelijk is om gevoelige
locaties te achterhalen door het gebruik van de totale duur en totale afgelegde
afstand van de activiteiten, in combinatie met het stratenplan van het gebied.
Dit soort aanvallen worden \textit{inferentieaanvallen} genoemd. Het traject
afgelegd binnenin de EPZ kan worden afgeleid met behulp van de totale afstand
van de activiteit en de zichtbare afstand, afgelegd buiten de EPZ.\ De afstand
binnenin de EPZ kan worden gemapt op het stratennetwerk, om zo alle mogelijke
routes te bekomen die de gebruiker kan afgelegd hebben binnenin de EPZ.\ Door
dit mechanisme toe te passen op alle activiteiten en geleidelijk aan punten te
schrappen die niet voor alle activiteiten een mogelijk eindpunt zijn, kan een
intersectie gevonden worden die uiteindelijk de gevoelige locatie oplevert. Dit
punt is dan de gevoelige locatie.

Deze thesis onderzoekt mogelijke implementaties van dergelijke
inferentie-aanvallen wanneer de afstand niet gekend is. Als alternatieve
gegevens worden de snelheid en het tempo van de activiteiten gebruikt, in
combinatie met gps-punten. Deze gevolgde methode bestaat uit drie delen. In de
eerste stap wordt de gemiddelde snelheid en de totale duur gebruikt om de
totale afstand te berekenen. Ten tweede worden de gps-punten gebruikt om de
afgelegde afstand buiten de EPZ te berekenen. Om dit zo accuraat mogelijk uit
te kunnen voeren, worden smoothing- en map-matchingstrategieën bestudeerd om de
best mogelijke resultaten te verkrijgen. Deze twee berekende waarden kunnen in
de derde stap worden gebruikt om de interferentieaanval uit te voeren. De
resultaten van deze aanval zullen worden vergeleken met de resultaten van
eerdere implementaties van dit soort aanval.

Met de juiste afstemming van de parameters van het smoothing-algoritme kan een
succespercentage tot 75\% worden bereikt. Dit is lager dan eerdere
implementaties van deze aanval, wat te verwachten is vanwege het type gegevens
dat wordt gebruikt. Voornamelijk doordat gps-data soms fouten bevat zoals
gps-drift, signaalverlies, gps-bounce, zal de afstand niet altijd even
nauwkeurig berekend kunnen worden. Doordat er zoveel punten nodig zijn,
resulteren kleine afwijkingen op elk punt in een grote afwijking op de
berekende afstand. Maar met dit onderzoek hebben we kunnen aantonen dat een
dergelijke aanval mogelijk is en een aanzienlijke nauwkeurigheidsscore behaalt,
ondanks het ontbreken van de totale afstand.

\textbf{Kernwoorden}: gps-locaties, privacy, endpoint privacy zone,
inferentie-aanval, snelheid
