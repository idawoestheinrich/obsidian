## Email Martin 21.08.2025
- Ähnlich wie auf den PCBs für CheapCal werden die Spannungen für den Preamp (+/- 5 V) lokal von zwei [[Low Dropout Regulators|LDOs]] erzeugt. Dies hat den Vorteil, dass die Op-Amps mit sauberen Referenzen versorgt werden. Als Eingangsspannung könnt ihr +/- 6 V oder +/- 7 V verwenden. Weniger kann je nach Kabellänge (und daher Spannungsabfall) in eurem Aufbau evtl. kritisch sein.
- Der Temperatursensor (**DS18B20U**) wird separat versorgt. So könnt ihr die Betriebsspannung und damit die Referenzspannung für die 1-wire Kommunikation selber wählen.
![[Screenshot 2025-08-21 at 10.08.14.png]]
- Alle Analog-Komponenten sind auf **GND** referenziert, die vom Temperatursensor auf **CHS**. 
	- Das hat den Grund, dass euch die Digitalelektronik so keinen Noise in die Messung mit der SiPM injiziert. Theoretisch könnt ihr die beiden Referenzen auf dem PCB miteinander verbinden, davon würde ich aber *abraten*. 
	- Besser ist es, das am Power Supply zu machen.
- Als SiPM habe ich einen von Broadcom mit sehr hoher [[Photon Detection Efficiency|PDE]] bzw. Working Range verwendet. Damit habt ihr einen recht breiten Sensitivitätsbereich (ich hatte keine wirkliche Vorstellung davon, wie viel Licht ihr seht). Ist bei Mouser, Digi-Key etc. jederzeit erhältlich.
- In Sachen Kabel habe ich eine hybride Lösung gewählt. Die Bias-Spannung und das (verstärkte) Signal des SiPM laufen über MMCX, die anderen Spannungen/Referenzen/Signale über einen Stecker von Molex ([https://www.molex.com/en-us/products/part-detail/2023960807](https://www.molex.com/en-us/products/part-detail/2023960807)) mit dem wir gute Erfahrungen gemacht haben. Dazu gibt es fertig konfektionierte Kabel, siehe hier: [https://www.molex.com/en-us/part-list/0257?physical.circuitsMaximum=8](https://www.molex.com/en-us/part-list/0257?physical.circuitsMaximum=8)
- Das PCB ist vierlagig mit einem Standard-Layerstack von Würth ([https://www.wedirekt.com/de/](https://www.wedirekt.com/de/)). Die Bestellung könnte ich aber sonst auch für euch übernehmen.

## Wo den PCB bestellen 
[Christian Scharf](https://mattermost.web.cern.ch/hu-berlin/pl/rr4wfu6jb38sbybfguwhi773ih)
- Wenn du geschaut hast, ob alles passt könntest du hier ein Angebot einholen: [https://loch-leiterplatten.de/](https://loch-leiterplatten.de/)
- ein paar 100 m vom Institut
- sehr schnell und unkompliziert

[[Voltage-to-Current Converter for LED Stabilization]]
