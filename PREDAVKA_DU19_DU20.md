# PŘEDÁVKA DU.19 → DU.20

## CO JE NA GITHUBU (nahrané, ale kód to nečte správně)

### Obrázky den 1 — 10 souborů v img/m01/d01/:
- D1S0.png — Exteriér laboratoře, Volta řve z okna, Agent dole
- D1S1.png — Volta se zkumavkou na nose, Agent ve dveřích (intro + okruh 1)
- D1S1b.png — Volta zuří s papíry VOD/-NÍK (alternativa pro intro)
- D1S2.png — Skřípek utíká, Agent klidný, Volta se směje (akce po okruhu 1)
- D1S3.png — Řepák za dveřmi (stín, prsty ve škvíře), Volta a Agent uvnitř
- D1S4.png — Volta s výpočty u stolu (okruh 2 matika)
- D1S5.png — Kartičky RED/BLUE/GREEN, papoušek na okně (okruh 3 angličtina)
- D1S6.png — Keksík vletí oknem (akce po okruhu 3)
- D1S7.png — Chaos skříň s houbami, mapami, kompasem (okruh 4)
- D1-P.png — Předměty sběru

### Záložní obrázky (nahrané ale nepřiřazené):
- Gemini_9mn9pd — Volta přemýšlí, pirát ve dveřích (teplé barvy — pro pozdější dny)
- Gemini_ie7c98 — Nástěnka s mapou a červenými provázky
- Gemini_zbtb8t — Volta s vynálezem, spirály energie
- Gemini_s5imhe — Volta drží VOD/-NÍK, stará verze

### JSON scénář — mise01_scenar_d01.json (KOMPLETNÍ):
- 13 intro dialogů (nové — příběh, vysvětlení, sběr předmětů, hlášky)
- 4 okruhy × 10 otázek = 40 otázek
- VŠECH 40 otázek má vi (Volta intro), vs (Volta správně), vn (Volta špatně) — vtipné
- Akce dialogy se slangem (skibidi, sus, rizz, ohio)
- Scénky po okruzích
- Sběrové předměty (5 kusů)
- Závěrečné dialogy (10 replik)

## CO NEFUNGUJE (hlavní úkoly pro DU.20)

### 1. KRITICKÉ: Kód čte špatný soubor
- Frontend (`index.html`) načítá `mise01_scenar.json` (hlavní soubor s 20 dny)
- Den 1 v tom souboru má STARÉ dialogy bez nového intra
- `mise01_scenar_d01.json` má NOVÉ kompletní dialogy ale kód ho čte jen jako fallback
- **ŘEŠENÍ:** Sloučit data z mise01_scenar_d01.json do mise01_scenar.json (den 1)

### 2. KRITICKÉ: Bubliny nefungují na mobilu
- contain layout způsobuje že obrázek je malý nahoře, dole černá
- Bubliny pozicované v % ale % se počítají z obrazovky ne z obrázku
- Na portrait mobilu jsou bubliny mimo hlavy
- **ŘEŠENÍ:** Celý nový přístup k pozicování — buď img tag s position:relative a bubliny uvnitř, nebo JS výpočet contain offsetu

### 3. KRITICKÉ: Obrázky se nemění podle scény
- SCENE_MAP je v kódu ale bg() funkce to špatně parsuje
- Výsledek: okruh 2 (matika) ukazuje obrázek Skřípka místo Volty s výpočty
- **ŘEŠENÍ:** Přepsat bg() a sk() funkce, otestovat před pushem

### 4. Tlačítko Zpět chybí nebo je schované
### 5. Formulace některých otázek — "Číslo 7 090 má na místě desítek:" zní divně

## PRAVIDLA CO JSME DOHODLY (dodržet v DU.20)

### Bubliny:
- Vajíčkový tvar na ležato
- Špička dlouhá ostrá dolů k ústům
- VŽDY nad hlavou nebo mírně před obličejem postavy
- Auto-size podle textu (krátký = malá, dlouhý = větší)
- Text centrovaný v bublině
- Připnuté k hlavě — pozice z HEADS mapy per scéna

### Obrázky:
- Contain (celý obrázek viditelný, žádné ořezávání)
- Dialogy = obrázky se mění (vtipné detaily)
- Otázky = stabilní obrázek na celý okruh (klid)
- VŽDY studené světlo (modrá/šedá palette)

### Otázky:
- 3 pokusy, Volta pomáhá po každé špatné (text z vn)
- Po 3. špatné ukáže správnou a jde dál
- Otázkový panel VŽDY dole, stabilní, čitelný, žádné animace
- Písmena A–E u odpovědí

### Příběh:
- Volta vysvětlí situaci (piráti vykradli, ukradli vynálezy)
- Volta řekne co potřebuje (pomoc Agenta)
- Volta zmíní sběr předmětů (budou se hodit)
- Piráti hláškují slangem (skibidi, rizz, sus, ohio)
- Volta na slang reaguje zmateně
- Celé vtipné, akční, jako komiksový film

### Flow dne 1 podle POSTUP_TVORBY_DNE.md:
1. Video úvod (D1-S1.mp4, D1-S2.mp4) → přeskočit
2. Obrázek D1S1 + intro dialogy (13 replik)
3. Obrázek D1S1 + OKRUH 1: 10 otázek čeština
4. Video akce (D1-S3.mp4) → přeskočit
5. Obrázek D1S2 + akce dialog (Skřípek) + sběr
6. Obrázek D1S3 + scénka (Řepák za dveřmi)
7. Obrázek D1S4 + OKRUH 2: 10 otázek matika
8. Video akce (D1-S4.mp4) → přeskočit
9. Obrázek D1S3 + akce dialog (Řepák s kbelíkem) + sběr
10. Obrázek D1S5 + OKRUH 3: 10 otázek angličtina
11. Video akce (D1-S5.mp4) → přeskočit
12. Obrázek D1S6 + akce dialog (Keksík) + sběr
13. Obrázek D1S7 + OKRUH 4: 10 otázek chaos
14. Video závěr (D1-S6.mp4) → přeskočit
15. Obrázek D1S5 + závěrečné dialogy
16. Shrnutí — skóre + sebrané předměty

### Day picker:
- Obrázek pirátské lodi nahoře (vtipná scéna)
- Karty dnů s ikonkami odměn/předmětů

## CO NAČÍST NA ZAČÁTKU DU.20:
1. POSTUP_TVORBY_DNE.md (v projektu)
2. DEFINITIVNI_SPECIFIKACE_PRO_DU.md (v projektu)
3. Tuto předávku
4. mise01_scenar_d01.json na GitHubu (aktuální verze)
5. index.html na GitHubu (aktuální verze — přepsat celý)
