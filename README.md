# Tester

[Odkaz na aplikaci](https://mujmobil92.github.io/Fuck-ACR/)

 **Verze aplikace:** 1.4

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
    }
  ]
}
```

**Pole `correct`** musí obsahovat `"A"`, `"B"` nebo `"C"` a určuje, která z odpovědí je správná.

**Pole `uncertain`** je volitelné (`true`/`false`) a patří ke konkrétní otázce. Pokud u ní chybí, bere se jako `false` – staré JSON soubory bez tohoto pole tedy fungují beze změny. Nastavíš ho jen u těch otázek, kde si nejsi 100% jistý/á, že je uvedená odpověď správně – u testu i u seznamu správných odpovědí se pak vedle otázky zobrazí červený varovný štítek "Nejistá odpověď".

**Pole `note`** je volitelné a patří k celému souboru (na stejné úrovni jako `version`, `date`, `author`, `description`) – je to jednotný text od autora k celé sadě otázek. Zobrazí se v hlavičce testu spolu s ostatními metadaty. Chybí-li, nic se nezobrazí a starší JSON soubory bez tohoto pole fungují beze změny. Novým řádkem v textu (`\n`) lze zprávu rozdělit do víc odstavců.
