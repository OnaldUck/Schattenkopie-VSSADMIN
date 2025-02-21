# Schattenkopie-VSSADMIN
Schttenkopie nutzen um nicht nur geänderte sondern auch gelöschte Dateien wieder zu bekommen.
Man kann es wie folgt einschalten, auch wenn Computerschutz grau und deaktivert ist

![Image](https://github.com/user-attachments/assets/8a0597dc-fd57-41d4-aefe-e68d409ecc10)

<img width="500" alt="upd-01" src="https://user-images.githubusercontent.com/35377000/415622035-8a0597dc-fd57-41d4-aefe-e68d409ecc10.jpg">

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
