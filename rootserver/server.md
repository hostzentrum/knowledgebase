# Server

**Kann ich meinen Server Up-/Downgraden?**

Du kannst jederzeit deinen Server Up-/Downgraden.Die Funktion kannst du mit dem Button "Up-/Downgraden" auf der Serververwaltung öffnen.

**Wie lange dauert die Installation eines Servers?**

Eine Neuinstallation eines Serversdauert in der Regel wenige Minuten.

**Wie leere ich den Cache?**

Um sowohl den PageCache, die dentries und die inodes zu löschen führt man einfach folgenden Befehl auf seinem Linux-Rootserver aus:

```
# sync; echo 3 > /proc/sys/vm/drop_caches 
```

**Wie ändere ich den Hostname meines Rootservers?**

Um den Hostname deines Rootservers zu ändern führe den Befehl "**nano /etc/hostname**" aus. Hier kannst du deinen Hostname bearbeiten.
