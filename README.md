# Fuck AČR – Tester

🔗 **Odkaz na aplikaci:** [https://mujmobil92.github.io/Fuck-ACR/](https://mujmobil92.github.io/Fuck-ACR/)

:)

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
