# Documentatie anomaly detectie - Arduino Nano 33 BLE sense

**Exporteer het Edge Impulse model**
In Edge Impulse ga naar het model en vervolgens naar deployment. Kies er hier voor om het model te exporteren als Arduino library.
Druk op deploy, het model wordt nu gedownload naar de computer.

**Het model importeren in de Arduino IDE**
Nu het model gedownload is ga naar de Arduino IDE en ga boven in naar 'sketch', kies include library en vervolgens 'add .ZIP library'.
Voeg de via Edge Impulse gedownloade zip file toe. De library is nu toegevoegd aan de Arduino IDE. 

**Include het model in de code**
Open het bestand met de code, ga naar 'sketch' en kies weer 'include library'. Kies vervolgens de net toegevoede library.
In de aangeleverde code zal al een library included zijn. Deze moet dus vervangen worden door het gedownloade model.

<img width="212" alt="Scherm­afbeelding 2023-06-26 om 12 31 27" src="https://github.com/yorrid/tatasteel_geluidsopdracht/assets/32573944/1fec5564-5168-4b32-985c-77cc8215b981">

**Pas de coordinaten aan**
In de code worden de variabele LATITUDE en LONGITUDE defined. Deze variabele hebben een standaard waarden en deze zijn bij oplevering
de volgende waarden. LATITUDE: 52.359738439900134, LONGITUDE: 4.90831842044538. Pas deze waarden aan naar de coordinaten die de
gewenste locatie aanduiden.

<img width="326" alt="Scherm­afbeelding 2023-06-26 om 13 45 53" src="https://github.com/yorrid/tatasteel_geluidsopdracht/assets/32573944/65a59119-5fd4-419e-9621-59fcb9aa423e">

**Voeg het board toe aan Arduino IDE**
Het gebruikte board staat niet automatisch in de board manager van de IDE. Om dit board te kunnen selecteren en naar goed naar het board
te kunnen uploaden moet deze toegevoegd worden. Dit kan gedaan worden door middel van de board manager. Download de volgende board package:
Arduino Mbed OS Nano Boards. Het juiste board is vervolgens te vinden onder tools, board, Arduino Mbed OS Nano Boards, Arduino Nano 33 BLE

**Upload de code naar een Arduino Nano 33 BLE sense board**
Nu de coordinaten de gewenste locatie aanduiden is het tijd om de code te uploaden naar het board. De code is geoptimaliseerd voor een 
Arduino Nano 33 BLE sense, het is dan ook van belang dat er gebruik gemaakt wordt van dit board. Sluit het board aan op de computer
doormiddel van een usb kabel. Kies in de Arduino IDE via 'tools' de port die verschijnt na het aansluiten van het board. Kies ook het 
juiste board met behulp van de board manager. Wanneer de port en het board juist zijn geslecteerd druk links bovenin op het pijltje (Upload)

Het heeft wat tijd nodig om de code te compilen en vervolgens te uploaden. Wanneer dit proces klaar is, open de serial monitor even via het 
knopje helemaal rechts bovenin de hoek. Dit is puur om te checken of de upload goed is gelukt. Ziet alles er goed uit? Dan is de upload gelukt
en kan het board weer ontkoppeld worden van de computer.

**Download ArduinoBLE library**
Voor de connectie met een telefoon of computer moet de ArduinoBLE library gedownload worden. Dit kan met behulp van de library manager.

**Connectie met telefoon via bluetooth**
Om deze verbinding te kunnen maken is het downloaden van een app nodig, de app die nodig is heet 'nRF connect for mobile'. Met behulp van deze 
app kan het BLE (Bluetooth Low Energy) signaal van de Arduino opgepakt worden. Nadat de app gedownload is, open de app en zoek naar het device
genaamd 'Arduino sound anomaly' (dit is de default naam die aan het board is gegeven, deze naam kan veranderd worden in de code doormiddel 
van het aanpassen van de BLE.setLocalName("Arduino sound anomaly") regel).

<img width="335" alt="Scherm­afbeelding 2023-06-26 om 13 27 15" src="https://github.com/yorrid/tatasteel_geluidsopdracht/assets/32573944/7c5f73ed-e5bb-4b0f-843a-5e43c3867fbe">

Connect met het board en ga bovenin de app naar 'client', bij Digital druk op de hoge comma's en kies UTF-8, zet ook het pijltje met het streepje
eronder aan. Ga vervolgens bovenin naar de 'log' tab. Hier komt nu de voorgeprogrammeerde data binnen wanneer er een anomaly plaatsvindt.

Om de connectie te verbreken kan er gewoon op 'Disconnect' gedrukt worden. Wanneer er geen verbinding is met een central device zoals een telefoon
of een computer wordt de data in de serial monitor geprint inplaats van dat het verstuurt wordt naar het verbonden apparaat.
