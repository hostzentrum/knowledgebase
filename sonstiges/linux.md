# Linux

**Java 8 auf Linux Installieren**

Zuerst melden wir uns via SSH mit z.B. Putty auf den Server an.Nun führen wir folgenden Befehl aus:

1. Server Updaten:
2. `root@testserver ~ # apt update`
3. Benötigte Pakete installieren:
4. `root@testserver ~ # apt install apt-transport-https ca-certificates wget dirmngr gnupg software-properties-common -y`
5. Public Key für die Repository herunterladen und hinzufügen:
6. `root@testserver ~ # wget -qO -` [`https://adoptopenjdk.jfrog.io/adoptopenjdk/api/gpg/key/public`](https://adoptopenjdk.jfrog.io/adoptopenjdk/api/gpg/key/public) `| apt-key add - && add-apt-repository --yes` [`https://adoptopenjdk.jfrog.io/adoptopenjdk/deb/`](https://adoptopenjdk.jfrog.io/adoptopenjdk/deb/)
7. Server Updaten:
8. `root@testserver ~ # apt update`
9. Java 8 installieren:
10. `root@testserver ~ # apt install adoptopenjdk-8-hotspot -y`

Mit folgenden Command können wir die Java version überprüfen`root@testserver ~ # java -versionjava version "1.8.*_***"Java(TM) SE Runtime Environment (build 1.8.*_**-***)Java HotSpot(TM) 64-Bit Server VM (build **.**-**, mixed mode)`Die \* sind Platzhalter und müssen in diesem Fall nicht beachtet werden.

**Passwort in Linux ändern**

Zuerst melden wir uns via SSH mit z.B. Putty auf den Server an.Nun führen wir folgenden Befehl aus:`root@testserver ~ # passwd [Benutzer]`in unserem Fall:`root@testserver ~ # passwd root`Nun bekommen wir die Aufforderung ein neues Passwort einzutippen. Das Passwort, welches eingeben wird, ist nicht sichtbar.Nachdem wir das Passwort bestätigt haben, ist unser Passwort geändert.`root@testserver ~ # passwdNew password:Retype new password:passwd: password updated successfullyroot@testserver ~ #`

**Hostname in Linux ändern**

Zuerst melden wir uns via SSH mit z.B. Putty auf den Server an.Im laufenden Betrieb können wir folgenden Befehl nutzen:`root@testserver ~ # hostname NewHostname`Damit der Hostname gespeichert bleibt müssen wir mit einem Editor wie in unserem Fall nano folgende Datei ändern:`root@testserver ~ # nano /etc/hostname`Nun haben wir dort unseren aktuellen Hostname und können diesen ändern.Nachdem wir den gewünschten Hostname eingetragen haben können wir das ganze mit STRG+X & STRG+Y bestätigen.

**PHP 7.4 auf Debian 9/10 installieren**

Zuerst melden wir uns via SSH mit z.B. Putty auf den Server an.Nun führen wir folgenden Befehl aus:

1. Server Updaten:
2. `root@testserver ~ # apt update`
3. Benötigte Pakete installieren:
4. `root@testserver ~ # apt install sudo -y`
5. Public Key für die Repository herunterladen und hinzufügen:
6. `root@testserver ~ # sudo wget -O /etc/apt/trusted.gpg.d/php.gpg` [`https://packages.sury.org/php/apt.gpg`](https://packages.sury.org/php/apt.gpg)
7. Repository hinzufügen:
8. `root@testserver ~ # echo "deb` [`https://packages.sury.org/php/`](https://packages.sury.org/php/) `$(lsb_release -sc) main" | sudo tee /etc/apt/sources.list.d/php.list`
9. Server Updaten:
10. `root@testserver ~ # apt update`
11. PHP 7.4 installieren:
12. `root@testserver ~ # apt install php7.4 -y`
