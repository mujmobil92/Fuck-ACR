# Fuck AČR – Tester

Jednoduchý webový tester na procvičování otázek formou kvízu. Běží čistě v prohlížeči, žádný server ani instalace nejsou potřeba – stačí otevřít `index.html`.

## Jak to funguje

1. Otevři `index.html` v prohlížeči.
2. Nahraj JSON soubor s otázkami.
3. Vyber téma (nebo nech "Všechna témata") a odpovídej.
4. Špatně zodpovězené otázky se automaticky vrací zpět do fronty, dokud je nezodpovíš správně.

## Funkce

- **Kvíz s výběrem tématu** a promícháním otázek i odpovědí
- **Opakování špatných odpovědí** – špatně zodpovězená otázka se vrátí znovu (označená badgem "Opakování")
- **Přehled správných odpovědí** s vyhledáváním
- **Tmavý režim** (uloží se do prohlížeče, zůstává i po zavření)
- **Automatické ukládání postupu** – reload stránky tě vrátí přesně tam, kde jsi skončil/a
- **Detekce offline stavu** – banner + zákaz nahrávání souboru bez připojení
- **Reset testu** s potvrzením, ať omylem nesmažeš rozpracovaný postup
- **Loading obrazovka** při pomalém načítání Bootstrapu z CDN

## Formát JSON souboru s otázkami

```json
{
  "version": "1.0",
  "date": "2026-07-16",
  "author": "Tvoje jméno",
  "description": "Krátký popis sady otázek",
  "questions": [
    {
      "topic": "Název tématu",
      "question": "Znění otázky?",
      "A": "Odpověď A",
      "B": "Odpověď B",
      "C": "Odpověď C",
      "correct": "B"
    }
  ]
}
```

**Pole `correct`** musí obsahovat `"A"`, `"B"` nebo `"C"` a určuje, která z odpovědí je správná.

## Poznámky

- Aplikace vyžaduje připojení k internetu (Bootstrap CSS/JS a ikony se načítají z CDN).
- Postup testu se ukládá do `localStorage` prohlížeče – při vymazání dat prohlížeče se ztratí.
- Otestováno v moderních prohlížečích (Chrome, Firefox, Edge, Safari).
