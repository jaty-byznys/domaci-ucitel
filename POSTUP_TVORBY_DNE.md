# POSTUP TVORBY JEDNOHO DNE — UNIVERZÁLNÍ ŠABLONA

## STRUKTURA KAŽDÉHO DNE

Každý den má tento pevný flow:

1. **ÚVODNÍ VIDEO** (5s, přeskočit tlačítko)
2. **OBRÁZEK 1 + intro dialogy** (klik pro pokračování)
3. **OBRÁZEK 1 + OKRUH 1: 10 otázek** (Volta se ptá v bublině, dítě vybírá odpověď, Volta reaguje)
4. **VIDEO AKCE 1** (vtipná scénka — pauza/odpočinek pro dítě po 10 otázkách)
5. **OBRÁZEK 2 + dialogy akce + sběr předmětu + scénka po okruhu 1**
6. **OBRÁZEK 2 + OKRUH 2: 10 otázek**
7. **VIDEO AKCE 2** (pauza/odpočinek)
8. **OBRÁZEK 3 + dialogy akce + sběr předmětu + scénka po okruhu 2**
9. **OBRÁZEK 3 + OKRUH 3: 10 otázek**
10. **VIDEO AKCE 3** (pauza/odpočinek)
11. **OBRÁZEK 4 + dialogy akce + sběr předmětu + scénka po okruhu 3**
12. **OBRÁZEK 4 + OKRUH 4: 10 otázek** (chaos — mix předmětů)
13. **ZÁVĚREČNÉ VIDEO**
14. **OBRÁZEK ZÁVĚR + závěrečné dialogy + shrnutí dne + sebrané předměty**

**Celkem na den: 40 otázek (4 × 10), 5 videí, 4 obrázky + 1 závěrečný obrázek, předměty**

---

## PROČ PO KAŽDÝCH 10 OTÁZKÁCH VIDEO

Dítě po 10 otázkách potřebuje pauzu. Video = odpočinek, zábava, příběhový posun. Dítě se směje, sleduje co se děje, a pak je připravené na dalších 10. Bez toho je to dril a dítě to zavře.

---

## CO MUSÍ OBSAHOVAT KAŽDÝ OBRÁZEK

Obrázek se odvíjí od dialogů které na něm poběží. Pokud se v dialogu mluví o postavě nebo je na ni narážka, MUSÍ být na obrázku.

Postup:
1. Přečti dialogy které poběží na daném obrázku
2. Vypiš VŠECHNY postavy které mluví nebo jsou zmiňované
3. Tyto postavy MUSÍ být na obrázku
4. Scéna musí odpovídat tomu co se právě stalo (po videu se změní situace)

---

## VIZUÁLY NA KAŽDÝ DEN — CHECKLIST

| # | Typ | Co to je | Kdo na tom musí být |
|---|-----|----------|---------------------|
| 1 | Úvodní video | Příchod, vstup do situace | Podle scénáře |
| 2 | Obrázek 1 | Intro dialogy + okruh 1 otázky | Volta + Agent + kdo mluví v intro |
| 3 | Video akce 1 | Vtipná akce po okruhu 1 | Podle scénáře akce |
| 4 | Obrázek 2 | Dialog akce + okruh 2 otázky | Volta + Agent + kdo přišel v akci |
| 5 | Video akce 2 | Vtipná akce po okruhu 2 | Podle scénáře akce |
| 6 | Obrázek 3 | Dialog akce + okruh 3 otázky | Volta + Agent + nová postava |
| 7 | Video akce 3 | Vtipná akce po okruhu 3 | Podle scénáře akce |
| 8 | Obrázek 4 | Dialog akce + okruh 4 (chaos) | Volta + Agent + kdo je ve scéně |
| 9 | Závěrečné video | Uzavření dne | Podle scénáře |
| 10 | Obrázek závěr | Závěrečné dialogy + shrnutí | Volta + Agent + kdo je přítomen |
| 11 | Předměty | Sběrové předměty dne | Na bílém pozadí, 2D cartoon |

**Celkem: 5 videí + 5 obrázků + 1 předměty = 11 vizuálů na den**

---

## FORMÁT PROMPTŮ PRO OBRÁZKY (GEMINI)

Struktura promptu:
```
Popis scény. Postava1 (ref.X) dělá/stojí kde. Postava2 (ref.Y) dělá/stojí kde. Detaily prostředí. Emoce a atmosféra. Studené světlo. 16:9
```

Referenční čísla postav:
- 1 = Dr. Volta
- 2 = Agent K
- 3 = Skřípek
- 4 = Řepák
- 5 = Keksík (papoušek)
- 6 = Kotva (Pirátka)
- 7 = Krivák

Pravidla:
- Vždy končit: `Studené světlo. 16:9`
- Postavy popisovat přes referenční čísla
- Popisovat co postavy DĚLAJÍ, ne jen že tam jsou
- Pokud je na obrázku nová postava, popsat její vstup

---

## FORMÁT PROMPTŮ PRO VIDEA (KLING AI 3.0)

- 5 sekund
- 1928×1072, H264
- Tiché (bez zvuku)
- Popis pohybu a akce, ne statický popis

---

## JAK VYTVOŘIT DEN — KROK ZA KROKEM

### Krok 1: Přečti kompletní scénář dne (od UH)
- Úvod, všechny 4 okruhy, akce, scénky, závěr

### Krok 2: Rozděl scénář na bloky
- Blok 1: Úvod + okruh 1
- Blok 2: Akce 1 + scénka + okruh 2
- Blok 3: Akce 2 + scénka + okruh 3
- Blok 4: Akce 3 + scénka + okruh 4 (chaos)
- Blok 5: Závěr

### Krok 3: Pro každý blok urči
- Jaké postavy mluví v dialogu?
- Jaké postavy jsou zmiňované?
- Co se změnilo oproti předchozímu bloku (kdo přišel/odešel)?
→ Z toho vyplyne KDO musí být na obrázku

### Krok 4: Napiš prompty
- 5 promptů na obrázky (podle postav a scény)
- 5 promptů na videa (podle akcí)
- 1 prompt na předměty

### Krok 5: Nori vygeneruje vizuály
- Obrázky v Gemini
- Videa v Kling AI 3.0
- Pošle do chatu DU

### Krok 6: DU nahraje na GitHub
- `img/m{mise}/d{den}/D{den}S{scena}.png`
- `video/m{mise}/d{den}/D{den}-S{scena}.mp4`
- `img/predmety/den{den}_sber.png`

### Krok 7: DU zapojí do kódu
- Aktualizuje `mise{XX}_scenar.json` s cestami k obrázkům a videím
- Obrázky jako pozadí pro otázkové bloky
- Videa jako pauzy mezi okruhy

---

## POJMENOVÁNÍ SOUBORŮ

Obrázky: `D{den}S{číslo}.png`
- S1 = úvodní scéna / obrázek pro intro + okruh 1
- S2 = obrázek po akci 1 / pro okruh 2
- S3 = obrázek po akci 2 / pro okruh 3
- S4 = obrázek po akci 3 / pro okruh 4
- S5 = závěrečný obrázek

Videa: `D{den}-S{číslo}.mp4`
- S1 = úvodní video
- S2 = video akce po okruhu 1
- S3 = video akce po okruhu 2
- S4 = video akce po okruhu 3
- S5 = závěrečné video

Předměty: `D{den}-P.png`

---

## OKRUHY

- Okruh 1: tématický (čeština nebo matika)
- Okruh 2: tématický (matika nebo čeština)
- Okruh 3: tématický (angličtina / přírodověda / vlastivěda — střídá se)
- Okruh 4: CHAOS — mix všech předmětů, lehčí, zábavný
- Každý okruh = přesně 10 otázek, choice, 5 možností, odpověď nikdy první

---

## BUBLINY A UI

- Celá obrazovka = scénový obrázek na pozadí, 16:9
- Bubliny: bílé oválné, černý obrys, ostrá špička směrem k postavě
- Bublina vždy u hlavy postavy která mluví — pozice závisí na obrázku, postavy NEJSOU fixně vlevo/vpravo
- Otázkový panel: vždy dole přes scénu, možnosti A–E, vždy stejné místo, vždy stejný vzhled

### Flow otázky:
1. Volta řekne otázku ve své bublině (u jeho hlavy)
2. Dole se zobrazí otázkový panel s možnostmi A–E
3. Dítě klikne na odpověď
4. Odpověď se propíše do bubliny Agenta (u jeho hlavy) — jako by ji Agent řekl nahlas
5. Volta reaguje ve své bublině (vtipná hláška / nápověda)

### Otázkový panel:
- VŽDY na stejném místě, VŽDY stejný vzhled — dítě nemusí hledat očima
- Jednoduché barvy, výrazné ale nevýkřiklavé — fáze zklidnění a soustředění
- Písmo klidné, čitelné, dostatečně velké
- Žádné blikání, animace, rozptylování během odpovídání
- Pohyb/videa JEN mezi okruhy, NIKDY během otázek

### Obrázky pro otázky:
- Volta a Agent mohou být kdekoli na scéně — záleží na situaci a obrázku
- Prostor nad hlavami pro bubliny
