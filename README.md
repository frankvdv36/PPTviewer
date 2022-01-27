# PPTviewer
## Beschrijving
Bedoeling is om een scherm zichtbaar op te stellen in een winkel met daarop advertenties, nieuwigheden, contactgegvens, enz.  
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
- schakel sscreensaver uit
@xset s noblank
@xset s off
@xset -apms
- starten van de PPT bij opstarten of reboot
libreoffice --show /home/pi/PPT/VDVCOM.odp
## Eigen scripts en programma's

## Resultaten en opmerkingen

## Alternatieve oplossing
