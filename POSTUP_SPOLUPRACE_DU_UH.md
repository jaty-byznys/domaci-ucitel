# POSTUP SPOLUPRÁCE DU + UH
## Domácí Učitel — kdo co dělá, jak to funguje
### Datum: 8. dubna 2026

---

## KDO JE KDO

**DU (Domácí Učitel)** = technický chat. Dělá kód, data, frontend, GitHub, Vercel, Supabase. Má přístup ke všemu technickému.

**UH (Učitel Hrou)** = kreativní chat. Dělá příběh, scénáře, hlášky postav, prompty na obrázky. Dodává markdown scénáře.

**Nori** = kurýr mezi oběma chaty + rozhodovatel. Schvaluje, kontroluje, řeší spory.

---

## CO KDO DODÁVÁ

### DU dodává:
- **Datové JSONy s otázkami:** `mise01_zari.json`, `mise02_rijen.json` atd.
  - 800 otázek na misi (20 dní × 4 okruhy × 10 otázek)
  - Formát: choice, 5 možností, odpověď nikdy na prvním místě
  - Hinty ke každé otázce
- **Scénářový JSON:** `mise01_scenar.json`
  - Parsovaný z UH markdownu — obsahuje příběh + otázky dohromady
  - Toto je soubor, který čte aplikace
- **index.html** — kompletní frontend, kód aplikace
- **predmety.json** — seznam předmětů a témat
- Push na GitHub, deploy na Vercel, správa Supabase

### UH dodává:
- **Scénáře v markdownu** — den po dni
  - Úvodní dialog (intro)
  - Voltovy reakce na otázky (vi = intro k otázce, vs = správně, vn = špatně)
  - Akce po 5. otázce
  - Scénky mezi okruhy
  - Závěrečná scénka dne
  - Sběr předmětů
- **Prompty na obrázky/video** (budoucnost)

---

## FORMÁT SCÉNÁŘŮ (stabilní — DU na něj staví parser)

```
**Volta:** "text dialogu"
**Agent:** "text"
**Skřípek:** "text"
**Krivák:** "text"

**Volta:** "intro k otázce" → pole `vi` v JSONu
**Správně:** "reakce na správnou odpověď" → pole `vs`
**Špatně:** "reakce na špatnou odpověď" → pole `vn`

## ⚡ AKCE PO OTÁZCE 5
→ akce uprostřed okruhu (dialog + zpráva)

## SCÉNKA PO OKRUHU X
→ scéna mezi okruhy

## ZÁVĚREČNÁ SCÉNKA DNE
→ konec dne

🎁 **SBĚR:** popis předmětu
*(Na obrazovce: "text")*
```

### Postavy a jejich avatary v aplikaci:
| Postava | Avatar | Typ bubliny |
|---------|--------|-------------|
| Volta (Dr. Volta) | 🧪 | modrá (volta) |
| Agent K | 🕵️ | zelená (agent) |
| Skřípek | 😰 | červená (pirát) |
| Řepák | 🍖 | červená (pirát) |
| Kotva | ⚓ | červená (pirát) |
| Krivák | ☠️ | červená (pirát) |
| Papoušek | 🦜 | červená (pirát) |

---

## JAK VZNIKÁ JEDNA MISE — KROK ZA KROKEM

### 1. DU vytvoří otázky
- Podle osnovy 4. ročníku (soubor `osnova_4_rocnik_komplet.md`)
- 800 otázek, 20 dní, 4 okruhy/den
- Výstup: `mise01_zari.json`
- Nahraje na GitHub

### 2. UH napíše scénáře
- Den po dni v markdownu
- Příběhový rámec: Volta, piráti, mise
- Výstup: markdown soubory se scénáři

### 3. Nori předá scénáře z UH do DU

### 4. DU parsuje markdown → JSON
- Spojí otázky (z kroku 1) + příběh (z kroku 2)
- Výstup: `mise01_scenar.json`
- Nahraje na GitHub

### 5. Aplikace čte `mise01_scenar.json`
- Vercel automaticky deployne po push na GitHub
- Appka zobrazí příběh + otázky

---

## PRAVIDLA PUSHOVÁNÍ NA GITHUB

**Repo:** `github.com/jaty-byznys/domaci-ucitel` (branch: main)

| Soubor | Kdo pushuje | Poznámka |
|--------|-------------|----------|
| `index.html` | DU | Frontend, kód. UH nesahá. |
| `mise01_zari.json` | DU | Čistá data — otázky |
| `mise01_scenar.json` | DU | Parsovaný scénář (otázky + příběh) |
| `predmety.json` | DU | Seznam předmětů |
| `okruhy/*.json` | DU | Starý systém (procvičování) |
| Markdown scénáře | UH → Nori → DU | UH píše, Nori přenáší, DU parsuje |

**Klíčové pravidlo:** Na jeden soubor sahá vždy jen jeden chat. Žádné paralelní edity.

---

## TECHNICKÁ INFRASTRUKTURA

| Co | Kde | Přístup |
|----|-----|---------|
| Živá appka | domaci-ucitel.cz | Vercel, auto-deploy |
| Záložní URL | domaci-ucitel.vercel.app | Vercel |
| Kód | github.com/jaty-byznys/domaci-ucitel | PAT token (do 7.5.2026) |
| Backend | Supabase (ydzlvkgrjkytalgcnsie) | EU/Londýn |
| Doména | Český hosting (ch115802) | — |

---

## STAV K 8. DUBNU 2026

- ✅ Mise 1 (září): 800 otázek hotových (`mise01_zari.json`)
- ✅ Scénáře dny 1–3 hotové (v `mise01_scenar.json`)
- ✅ Frontend v0.5.1 s MissionScreen funguje
- ✅ Den 1 plně hratelný (příběh + otázky + choice)
- 🔄 Mise 2 (říjen): dny 1–5 rozpracované (DU)
- ⏳ Scénáře dny 4–20 mise 1 (čeká na UH)
- ⏳ Mise 2–10 (data i scénáře)
