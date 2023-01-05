# DDOS Protection

## DDOS Protection

Wir schützen unser Netzwerk sehr effektiv gegen DDOS Angriffe, durch den Einsatz von Erkennungssoftware und Vorfilter. Die Protection erkennt und filtert automatisch den "Bad Traffic" und schützt IP-Adressen gegen DDOS Angriffe (bis zu 800Gbit).\


Wenn Sie eine Webseite (HTTP oder HTTPS) vor DDOS Angriffen schützen wollen, empfehlen wir zusätzlich für eine höhere Effizienz den Einsatz der Layer 7 Protection. Ein DDOS Angriff kann mittels der Layer 7 Protection deutlich schneller erkannt und gefiltert werden. Sinnvoll ist es bei der Verwendung von SSL das Zertifikat in der Firewall Software zu hinterlegen.

Während eines Angriffes bleibt der Server weiter erreichbar und Sie können die Dienste normal nutzen. Nicht relevante Ports werden solange der Angriff andauert geblockt, zum Beispiel icmp für Ping abfragen.

\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_

### Informationen zur Layer 7 DDoS Protection

Es gibt verschiedene Arten von DDoS (Distributed Denial of Service) Angriffen. Grundsätzlich ist unter einem DDoS eine „Verweigerung des Dienstes“ zu verstehen, welche absichtlich durch eine Vielanzahl an Anfragen zustande kommt und so zu einer Überlastung des Datennetzes bzw. des Servers führt.

DDoS Angriffe können hierbei auf verschiedene Schichten zielen (siehe ISO/OSI-Schichtenmodell). Im Vergleich zu früher zielen aktuelle DDoS-Angriffe dabei häufig auf die oberste Schicht (Layer 7). Layer 7 ist die Anwendungsschicht und dient zur Bereitstellung von Funktionen für die Anwendungen und ist für die Dateneingabe und –ausgabe zuständig.

Die Layer-7-Attacken zielen speziell auf die zu Layer 7 gehörigen Protokolle wie Telnet, FTP, NNTP, HTTP oder SMTP. Im Vergleich zu anderen DDoS-Attacken erfordern Layer-7-Angriffe weit weniger Bandbreite und Pakete, um zu einer Störung der Dienste zu führen. Ein Low-Level Protokoll-Angriff wie beispielsweise SYN-Flood erfordert eine riesige Anzahl von Paketen, um einen effektiven DDoS-Angriff durchzuführen, während es bei einer Layer-7-Attacke nur eine begrenzte Anzahl von Paketen braucht, um einen großen DDoS-Angriff umzusetzen.

Am meist verbreitesten unter den Layer-7-Attacken ist das HTTP Flooding. Hierbei wird eine HTTP-Anforderung an den betroffenen Server gesendet und nutzt dabei erhebliche Ressourcen und obwohl die Anzahl der Pakete hierbei begrenzt ist, nutzen diese alle Serverressourcen voll aus und führen zu einer Verweigerung der Dienste.

Die Layer 7 Protection wird auf Ihren Wunsch von uns aktiviert, auch die Hinterlegung des Zertifikats in der Firewall Software erfolgt durch uns.

\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_

### Was passiert bei einem Angriff

* ICMP / IGMP (u.a. PING) wird verworfen
* &#x20;__ UDP Source-Port 19, 69, 111, 123, 137, 161, 389, 520, 1434, 1900, 9987, 11211 werden limitiert (10Mbit)
* &#x20;__ TCP / UDP Fragemente (Pakete größer als 1500 byte) werden verworfen
* &#x20;__ UDP Destination Port 9000 bis 9999 wird strikt gegen Teamspeak3 Pakete gefiltert
* &#x20;__ UDP Destination Port 27000 bis 29000 wird strikt gegen Source Engine Pakete gefiltert
* &#x20;__ UDP Destination Port 53 wird strikt gegen DNS Pakete gefiltert und erzwingt TCP Truncation
* &#x20;__ Bei aktiver HTTP Layer7 Mitigation wird sämtlicher TCP Traffic auf Port 80 und 443 durch einen Reverse Proxy geroutet
* &#x20;__ Bei aktiver HTTP Layer7 Mitigation muss Cloudflare deaktiviert werden, da sonst eine Schleife der DNS Auflösung entsteht
* &#x20;__ Jeglicher Traffic (außer TCP / UDP) und wird blockiert

**Aller weiterer Traffic (TCP / UDP) wird strikt validiert:**

* &#x20;__ TCP Verbindungen sind nur möglich, sofern zuvor ein TCP SYN oder SYN-ACK Paket gesendet und akzeptiert wurde, die Filter verhalten sich hierbei wie eine Art asynchrone Stateful Firewall für Serveranwendungen. Der Aufbau einer ersten Verbindung (SYN bzw. SYN-ACK) dauert womöglich deutlich länger oder wird erstmalig unterbrochen, Webpräsenzen laden ggf. etwas langsamer
* &#x20;__ UDP Verbindungen sind nur möglich, sofern diese von einem „validen Client“ durchgeführt werden, Spoofing wird durch einen intelligenten Abgleich aller Verbindungsparameter unterbunden

\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_

### Port für den Betrieb von Gameservern

Die folgenden Ports wurden speziell für den Betrieb von Gameservern implementiert:

* &#x20;__ 2300-2400: DayZ and Arma 3, as well as Arma 3 Query
* &#x20;__ 5761-5794: Atlas
* &#x20;__ 7000-8999: Generic Games
* &#x20;__ 9000-9999: Teamspeak3
* &#x20;__ 12800-13100: Hurtworld
* &#x20;__ 19132: Minecraft Pocket Edition
* &#x20;__ 22000-22020: Rage-MP / MTA
* &#x20;__ 22126: Rage-MP / MTA
* &#x20;__ 23000-23200: Battlefield
* &#x20;__ 27000-28000: Alle Source Engine / Query Games wie Counter Strike 1.6, Counter Strike Source, Counter Strike GO, The Ship, Garrys Mod, Nuclear Dawn, Call of Duty Modern Warfare 3, Starbound, Space Engineers, 7 Days to Die, Rust, Quake Live, ARK: Survival Entwickelt, Valheim, Mordhau
* &#x20;__ 30000-32000: FiveM GTA-MP
* &#x20;__ 36123-36128: Stormworks

\
\


\
