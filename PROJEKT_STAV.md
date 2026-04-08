# DOMÁCÍ UČITEL — STAV PROJEKTU
## Poslední aktualizace: 8. dubna 2026

---

## CO TO JE
Webová aplikace pro procvičování učiva 4. ročníku ZŠ.
Živě na: https://domaci-ucitel.vercel.app
Repo: https://github.com/jaty-byznys/domaci-ucitel

---

## ARCHITEKTURA

### index.html
Aplikace. Obsahuje vzhled (CSS) a logiku (React/JS).
Načítá predmety.json → zobrazí předměty → dítě klikne na téma → fetch načte JSON soubor s cvičeními.
TENTO SOUBOR SE UŽ NEMĚNÍ (pokud neopravujeme bug).

### predmety.json
Seznam předmětů a témat. Ke každému tématu cesta k souboru.
Mění se JEN když přidáme nové téma (přidá se jeden řádek).

### Složky s cvičeními
Každé téma = jeden JSON soubor. Minimálně 100 úloh na soubor.
Všechny úlohy jsou typu "choice" s 5 možnostmi.
Distraktory musí být věrohodné, ne zjevné blbosti.

Struktura složek:
```
cestina/
  01_stavba_slova.json          ← HOTOVO (100 úloh)
  02_vyjmenovana_slova_B.json   ← CHYBÍ
  02_vyjmenovana_slova_L.json   ← CHYBÍ
  02_vyjmenovana_slova_M.json   ← CHYBÍ
  02_vyjmenovana_slova_P.json   ← CHYBÍ
  02_vyjmenovana_slova_S.json   ← CHYBÍ
  02_vyjmenovana_slova_V.json   ← CHYBÍ
  02_vyjmenovana_slova_Z.json   ← CHYBÍ
  03_slovni_druhy.json           ← CHYBÍ
  04_podstatna_jmena.json        ← CHYBÍ
  05_slovesa.json                ← CHYBÍ
  06_stavba_vety.json            ← CHYBÍ
  07_cteni_s_porozumenim.json    ← CHYBÍ

matika/
  01_ciselny_obor.json           ← CHYBÍ
  02_scitani_odcitani.json       ← CHYBÍ
  03_nasobeni.json               ← CHYBÍ
  04_deleni.json                 ← CHYBÍ
  05_zlomky.json                 ← CHYBÍ
  06_geometrie.json              ← CHYBÍ
  07_jednotky.json               ← CHYBÍ
  08_slovni_ulohy.json           ← CHYBÍ
  09_zavorky.json                ← CHYBÍ
  10_prace_s_daty.json           ← CHYBÍ

prirodoveda/
  01_ziva_neziva_priroda.json    ← CHYBÍ
  02_houby.json                  ← CHYBÍ
  03_rostliny.json               ← CHYBÍ
  04_zivocichove.json            ← CHYBÍ
  05_ekosystemy.json             ← CHYBÍ
  06_neziva_priroda.json         ← CHYBÍ
  07_rocni_obdobi.json           ← CHYBÍ
  08_clovek_a_zdravi.json        ← CHYBÍ
  09_ochrana_prirody.json        ← CHYBÍ

vlastiveda/
  01_orientace_na_mape.json      ← CHYBÍ
  02_ceska_republika.json        ← CHYBÍ
  03_pravek.json                 ← CHYBÍ
  04_slovane.json                ← CHYBÍ
  05_premyslovci.json            ← CHYBÍ
  06_lucemburkove.json           ← CHYBÍ
  07_hus_a_husitstvi.json        ← CHYBÍ

anglictina/
  01_barvy_cisla.json            ← CHYBÍ
  02_rodina.json                 ← CHYBÍ
  03_zvirata.json                ← CHYBÍ
  04_jidlo_piti.json             ← CHYBÍ
  05_obleceni.json               ← CHYBÍ
  06_casti_tela.json             ← CHYBÍ
  07_skola.json                  ← CHYBÍ
  08_dum_pokoj.json              ← CHYBÍ
  09_dny_mesice.json             ← CHYBÍ
  10_to_be.json                  ← CHYBÍ
  11_to_have.json                ← CHYBÍ
  12_pritomny_cas.json           ← CHYBÍ
  13_can.json                    ← CHYBÍ
  14_there_is_are.json           ← CHYBÍ
  15_predlozky.json              ← CHYBÍ
```

---

## FORMÁT SOUBORU S CVIČENÍMI

Každý soubor je JSON s touto strukturou:
```json
{
  "id": "CJ4-06",
  "name": "Stavba slova",
  "order": 0,
  "prerequisite": null,
  "skills": [
    {
      "id": "CJ4-06-01",
      "name": "Kořen slova",
      "difficulty": 1,
      "theory": "Stručné vysvětlení pro dítě...",
      "tasks": [
        {
          "id": "CJ4-06-01-001",
          "type": "choice",
          "question": "Otázka...",
          "options": ["A", "B", "C", "D", "E"],
          "answer": "B",
          "hint": "Nápověda..."
        }
      ]
    }
  ]
}
```

Pravidla:
- Typ úlohy: VŽDY "choice"
- Počet možností: VŽDY 5
- Distraktory: věrohodné, ne zjevné nesmysly
- Minimálně 100 úloh na soubor
- Hinty: krátké, vedou k přemýšlení, neříkají odpověď

---

## POSTUP PRÁCE

1. Claude vytvoří soubor s cvičeními (např. cestina/02_vyjmenovana_slova_B.json)
2. Nori stáhne a nahraje na GitHub do správné složky
3. Pokud je to nové téma, Claude aktualizuje predmety.json (přidá řádek)
4. Vercel automaticky nasadí

---

## CO JE HOTOVO
- [x] index.html — aplikace s fetch architekturou
- [x] predmety.json — seznam všech témat
- [x] cestina/01_stavba_slova.json — 100 úloh
- [x] osnova_4_rocnik_komplet.md — kompletní osnova

## CO JE DALŠÍ
- [ ] cestina/02_vyjmenovana_slova_B.json
- [ ] cestina/02_vyjmenovana_slova_L.json
- [ ] ... (postupně všech 54 souborů)

---

## POZNÁMKY
- Starý db.json a 01_stavba_slova.json v kořeni repo jsou zastaralé, smazat až bude nová verze funkční
- Osnova je v souboru osnova_4_rocnik_komplet.md
