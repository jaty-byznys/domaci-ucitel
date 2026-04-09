# PŘEDÁVKA DU.15 → DU.16

## CO JE HOTOVO

### Otázky — 10 misí, 8000 otázek, celý školní rok
Všechny na GitHubu (`jaty-byznys/domaci-ucitel`, branch main):
- mise01_zari.json až mise10_cerven.json
- Každá mise = 20 dní × 4 okruhy × 10 otázek = 800 otázek
- Pattern okruhu 3: AJ dny 1,2,5,6,7,10,11,12,15,16,17,20 / PR dny 3,8,13,18 / VL dny 4,9,14,19
- Validace: 0 chyb, odpověď nikdy na 1. místě, unikátní ID

### Vizuály den 1 — na GitHubu
**Obrázky** (`img/m01/d01/`):
- D1S1.png — Agent přichází k laboratoři (intro)
- D1S2.png — Volta v zničené laboratoři s papíry (pozadí pro okruh 1 čeština + okruh 2 matika)
- D1S3.png — Skřípek vyskočí (akce po okruhu 1)
- D1S4.png — Řepák s kbelíkem (akce po okruhu 2)
- D1S5.png — Keksík vletí oknem (akce okruh 3)
- D1S6.png — Závěrečná scéna, Volta + Agent, klid

**Videa** (`video/m01/d01/`):
- D1-S1.mp4 až D1-S6.mp4 (5s klipy, Kling AI 3.0, 1928×1072, H264, tiché)
- D1-P.mp4 (předměty animované)

**Postavy** (`img/postavy/`): volta.png, agent.png, skripek.png, repak.png, keksik.png, piratka.png, krivak.png

**Předměty** (`img/predmety/`): den01_sber.png

**Scénářový JSON**: mise01_scenar_d01.json — příběh + otázky + Voltovy reakce (vi/vs/vn) + napojení obrázků a videí

### Scénáře od UH v projektu
MISE1_DEN01 až MISE1_DEN11_KOMPLET_SCENAR.md — kompletní scénáře s dialogy, akcemi, sběry, prompty na obrázky

---

## HLAVNÍ ÚKOL DU.16: FRONTEND PROTOTYP DEN 1

### VIZUÁLNÍ KONCEPT — co Nori opakovaně specifikovala:

1. **Celá obrazovka = SCÉNA** — scénový obrázek jako pozadí na celou plochu, 16:9 širokoúhlé
2. **PC nebo mobil naležato** — NE mobilní portrait layout
3. **Komiksové bubliny** — BÍLÉ OVÁLNÉ bubliny s ČERNÝM obrysem a OSTROU ŠPIČKOU směrem k hlavě postavy (viz ukázka komiks bubliny co Nori poslala)
4. **Volta dává otázku** v bublině u své hlavy (bokem na scéně)
5. **Agent odpovídá** — když dítě klikne odpověď, ta se propisuje do bubliny u Agenta (jako by to řekl on)
6. **Dialog mezi nimi** — Volta se ptá, Agent odpovídá, Volta reaguje vtipnou hláškou
7. **Otázková karta** — panel dole přes scénu s možnostmi A–E
8. **Žádný pohyb během otázek** — klid na práci, pohyb/videa JEN mezi okruhy (scénky, akce)
9. **ŽÁDNÉ RETRO** — moderní design, inspirovat se tím co letí
10. **Barevnost** — z postav (Volta bílá/oranžová, piráti červená) + oživení barvami papouška (zeleno-červeno-modrá)
11. **Vtipné prvky** — myš po stránce, papoušek ji honí, chytlavé hlášky
12. **Dítě se musí řehtat** — hlášky geniální, ne školní

### CO NEPLATÍ (Nori zamítla):
- Mobilní portrait layout
- Chatové bubliny/messenger styl
- Tmavé barevné bordery na bublinách
- Emoji místo obrázků postav
- Retro design
- Nudné korporátní UI

### Flow dne:
1. Video intro (5s, přeskočit tlačítko)
2. Dialog (bubliny na scéně) → klik pokračovat
3. Okruh 1–4: statický obrázek + Volta ptá se v bublině + otázková karta dole + Agent odpovídá
4. Po 5. otázce: akce (video + dialog + sběr předmětu)
5. Scénka mezi okruhy
6. Závěr dne: shrnutí + sebrané předměty

### Pozadí pro okruhy:
- Okruh 1 (čeština) + Okruh 2 (matika): D1S2.png (Volta v laboratoři)
- Okruh 3 (angličtina/chaos): D1S2.png nebo D1S5.png
- Akce: příslušný scénový obrázek (D1S3 Skřípek, D1S4 Řepák, D1S5 Keksík)
- Závěr: D1S6.png

---

## TECHNICKÉ DETAILY

- **GitHub**: jaty-byznys/domaci-ucitel (PAT v memory, nepsat do souborů!)
- **Vercel**: auto-deploy po push na main
- **Doména**: domaci-ucitel.cz
- **Frontend**: React (Babel, single-file index.html)
- **Supabase**: ydzlvkgrjkytalgcnsie (EU/London)
- **Obrázky z GitHubu**: https://raw.githubusercontent.com/jaty-byznys/domaci-ucitel/main/img/...

## WORKFLOW

1. UH píše scénáře → Nori předá
2. Nori dělá obrázky (Gemini) a videa (Kling AI 3.0) → nahraje sem do chatu
3. DU parsuje scénáře → JSON, nahrává vizuály na GitHub, staví frontend, kontroluje vtipnost hlášek

## CO NAČÍST NA ZAČÁTKU DU.16

1. Tento soubor (PREDAVKA_DU15_DU16.md) 
2. mise01_scenar_d01.json na GitHubu — data pro den 1
3. Scénáře v projektu: MISE1_DEN01 až DEN11
4. DEFINITIVNI_SPECIFIKACE_PRO_DU.md v projektu
5. Předchozí chaty pro kontext vizuálního designu
