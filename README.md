# Tester

[Odkaz na aplikaci](https://mujmobil92.github.io/Fuck-ACR/)

:)

## Formát JSON souboru s otázkami

```json
{
  "version": "1.0",
  "date": "2026-07-16",
  "author": "Tvoje jméno",
  "description": "Krátký popis sady otázek",
  "note": "Delší volitelná zpráva od autora k celé sadě otázek - třeba zdroj informací, upozornění na sporné otázky, poděkování apod. Klidně na víc řádků (\n = nový řádek).",
  "questions": [
    {
      "topic": "Název tématu",
      "question": "Znění otázky?",
      "A": "Odpověď A",
      "B": "Odpověď B",
      "C": "Odpověď C",
      "correct": "B"
    },
    {
      "topic": "Název tématu",
      "question": "Otázka, u které si nejsi jistý/á správností odpovědi?",
      "A": "Odpověď A",
      "B": "Odpověď B",
      "C": "Odpověď C",
      "correct": "B",
      "uncertain": true
    },
    {
      "topic": "Název tématu",
      "question": "Otázka se čtyřmi (nebo více) odpověďmi?",
      "A": "Odpověď A",
      "B": "Odpověď B",
      "C": "Odpověď C",
      "D": "Odpověď D",
      "correct": "D"
    }
  ]
}
```

**Odpovědi** se zapisují jako pole pojmenovaná velkými písmeny `"A"`, `"B"`, `"C"`, `"D"`, `"E"`, … (až `"Z"`). Počet odpovědí může být u každé otázky jiný – minimum jsou 2 odpovědi. Prázdné odpovědi (`""`) se ignorují. Při zobrazení otázky se odpovědi vždy náhodně zamíchají, takže písmeno v JSON souboru neurčuje pořadí na obrazovce.

**Pole `correct`** obsahuje písmeno správné odpovědi (např. `"A"`, `"C"`, `"D"`). Musí odpovídat některé z odpovědí, které otázka skutečně má – jinak se otázka při načtení přeskočí (podrobnosti se vypíšou do konzole prohlížeče).

**Pole `uncertain`** je volitelné (`true`/`false`) a patří ke konkrétní otázce. Pokud u ní chybí, bere se jako `false` – staré JSON soubory bez tohoto pole tedy fungují beze změny. Nastavíš ho jen u těch otázek, kde si nejsi 100% jistý/á, že je uvedená odpověď správně – u testu i u seznamu správných odpovědí se pak vedle otázky zobrazí červený varovný štítek "Nejistá odpověď".

**Pole `note`** je volitelné a patří k celému souboru (na stejné úrovni jako `version`, `date`, `author`, `description`) – je to jednotný text od autora k celé sadě otázek. Zobrazí se v hlavičce testu spolu s ostatními metadaty. Chybí-li, nic se nezobrazí a starší JSON soubory bez tohoto pole fungují beze změny. Novým řádkem v textu (`\n`) lze zprávu rozdělit do víc odstavců.
