# PPTviewer
## Beschrijving
Bedoeling is om een scherm zichtbaar op te stellen in een winkel met daarop advertenties, nieuwigheden, contactgegevens, enz.  
Bron is een PowerPoinT waarop alles wordt voorbereid. Libreoffice laat de PPT zien. 
Ook een autostart is nodig daar de Raspberry Pi aan het scherm wordt gemonteerd. Dus geen muis of toetsenbord. Wel bereikbaar via VNC.
## Bronnen
In de eerste cursus op raspberry.pindanet.be hebben we het volgende geleerd:
- Uitschakelen van screenblanking via lxterminal
- Opstarten van een programma in lxterminal 
- Idem maar nu met de automatische start van de PPT bij power-up of reboot 
- Met 'nano' de nodig aanpassing maken in AUTOSTART 
## Hardware
Hardware kan een PI3B+ zijn en als het kan een Zero2W.
## Software
File in /etc/xdg/lxsession/LXDE-pi/autostart
schakel screensaver uit
- @xset s noblank 
- @xset s off (screensaver Off)
- @xset -dpms (Display Power Management Signaling)
starten van de PPT bij opstarten of reboot
- libreoffice --show /home/pi/PPT/VDVCOM.odp
## Eigen scripts en programma's

## Resultaten en opmerkingen
De PPT wordt mooi zichtbaar in full screen. 
- Toch gebeurt het dat de PPT soms blijft hangen op een bepaalde silde. Met een muis bewegen of 'space' loopt deze weer verder.
- Met bullseye, Rasbian11, wordt bij Libreoffice de jablonen niet meegenomen van Microsoft naar Libreoffice. Witte achtergrond als resultaat.
Als het programma mooi opgestart en afgesloten wordt zijn er geen problemen.
- Er zijn wel problemen als de voeding plots uitvalt. Bij het opnieuw opstarten komen er vragen die moeten beantwoord worden (herstellen?)
- Daarom blijft bij het opstarten de vertoning uit. Manuele tussenkomst is dan nodig. Mogelijks kan dit met enkele instructies tijdens het opstarten voorkomen worden.  
## Alternatieve oplossing
Tijdens opzoekwerk naar een oplossing werd verwezen naar 'Screenly OSE'. https://www.screenly.io/ose/
Deze is geïnstalleerd na de installatie Raspberry pi OS, Buster. Nog niet geprobeerd op Bullseye. 
Bij opstarten komt Screenly automatisch op het scherm met daarop het IP adres waarmee kan gecommuniceerd worden.
Er zijn 2 mogelijkheden, ofwel file uploaden, ofwel URL aanduiden waar de info staat. 
Er kunnen meerdere files geselecteerd worden met een schakelaar om al of niet te vertonen.
Bij het heropstarten krijgt men het zelfde opstartscherm maar na een tijdje begint het systeem vanzelf met de laatste vertoning.
Let wel de PPT moet geëxporteerd worden. Iedere pagina wordt in dit geval een .png file. Er zijn meedere filetypes mogelijk maar nog niet uitgetest.
- Deze oplossing voldoent wel aan de verwachtingen. Zelfs bij spanningsonderbrekingen blijft het systeem na opstarten stabiel zonder manuele tussenkomsten.
