# Schattenkopie-VSSADMIN
Schttenkopie nutzen um nicht nur geänderte sondern auch gelöschte Dateien wieder zu bekommen.
Man kann es wie folgt einschalten, auch wenn Computerschutz grau und deaktivert ist

![computerschutz](https://github.com/user-attachments/assets/97c6affc-f2f2-4a38-b2e1-5beefa9d50b9)


```
wmic /namespace:\\root\default path SystemRestore call Enable d:\
```

Auf der Kommandozeile Schattenkopie erstellen
```
wmic shadowcopy call create Volume=d:\
```

Die Schattenkopie in einen Ordner mounten. Zunächst mit folgenden Kommando auflisten
```
vssadmin list shadows
```
anschliessend mit MKLINK in einen Ordner maounten. Der abschliessende Backslash ist wichtig
```
mklink /d a:\vss \\?\GLOBALROOT\Device\HarddiskVolumeShadowCopy1\
```

