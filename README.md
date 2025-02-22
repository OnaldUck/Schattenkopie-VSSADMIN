# Schattenkopie-VSSADMIN
Schttenkopie nutzen um nicht nur geänderte sondern auch gelöschte Dateien wieder zu bekommen.
Man kann es wie folgt einschalten, auch wenn [Computerschutz aktivieren] und [Erstellen] grau und deaktivert ist :-).

<img width="328" alt="computerschutz" src="https://github.com/user-attachments/assets/9e42a5f3-9f12-4046-acef-8c6f134d3b94" />
<img width="307" alt="computerschutz-erstellen" src="https://github.com/user-attachments/assets/b5b3ad98-199e-425c-8880-f4354cbfb23e" />

## Computerschutz einschalten
```
wmic /namespace:\\root\default path SystemRestore call Enable d:\
```

## Schattenkopie auf Kommandozeile erstellen
```
wmic shadowcopy call create Volume=d:\
```

## Die Schattenkopie in einen Ordner mounten

Zunächst mit folgenden Kommando auflisten
```
vssadmin list shadows
```
Anschliessend mit MKLINK in einen Ordner mounten. Der abschliessende Backslash ist wichtig
```
mklink /d a:\vss \\?\GLOBALROOT\Device\HarddiskVolumeShadowCopy1\
```
