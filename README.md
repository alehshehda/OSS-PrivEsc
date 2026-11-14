# Raport: Eskalacja uprawnień a ochrona systemowej bazy haseł

Dokumentacja projektowa z przedmiotu **Ochrona Systemów Operacyjnych** (Politechnika Wrocławska, Grupa 2) przygotowana w systemie LaTeX.

## Struktura rozdziałów (`chapters/`)

1. `1_wstep.tex` - Wstęp
2. `2_podstawy_teoretyczne.tex` - Podstawy teoretyczne
3. `3_case_study_1_eskalacja_pozioma.tex` - Studium przypadku 1: Eskalacja pozioma (`user1 -> user2`, Adam Rola)
4. `4_case_study_2_eskalacja_pionowa.tex` - Studium przypadku 2: Eskalacja pionowa (`user -> root`, Ruslan Hedz)
5. `5_case_study_3_ucieczka_z_kontenera.tex` - Studium przypadku 3: Ucieczka z kontenera (`container -> host`, Aleh Shehda)
6. `6_case_study_4_eksploatacja_jadra.tex` - Studium przypadku 4: Eksploatacja jądra systemu (`ring3 -> ring0`, Aliaksei Lapachuk)
7. `7_podsumowanie.tex` - Podsumowanie

## Układ projektu

```
main.tex                 szkielet dokumentu (kolejność części)
config/
  metadata.tex           dane dokumentu i przełączniki części opcjonalnych
  theme-pwr.tex          kolory, nazwy uczelni i wydziału, plik logo
preamble/                konfiguracja pakietów, makr, tabel, listingów i nagłówków
frontmatter/             strona tytułowa, streszczenie, spis skrótów
chapters/                rozdziały 1..7
images/
  cs1/..cs4/             katalogi na zrzuty ekranu i diagramy dla poszczególnych Case Studies
logos/                   logo uczelni
bib/
  references.bib         źródła (BibTeX)
  plabbrv-fixed.bst      polski styl bibliografii
```

## Najczęstsze makra

- **Rysunek:** `\Figure[0.8]{cs1/plik.png}{Podpis}{fig:cs1-etykieta}` (ścieżka względem `images/`).
- **Tabela:** podpis nad tabelą, `\tablefont`, `booktabs`; kolumny rozciągliwe `Y`/`Z` w `tabularx`, stałe `L{..}`/`C{..}`/`R{..}`.
- **Listing:** domyślnie styl `terminal`; kod: `\begin{lstlisting}[style=code, language=Python, caption={...}, label={lst:...}]`.
- **Skróty i ścieżki w tekście:** `\code{}`, `\file{}`, `\cmd{}`, `\hash{}`.
- **Cytowanie:** dodaj wpis do `bib/references.bib` i użyj `\cite{klucz}`.

## Kompilacja

Silnik: **pdfLaTeX** + **BibTeX**:

```powershell
pdflatex main.tex
bibtex main
pdflatex main.tex
pdflatex main.tex
```

