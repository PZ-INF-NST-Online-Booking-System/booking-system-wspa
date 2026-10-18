# Online Booking System

> Projekt zespołowy systemu informatycznego, cz. 1 (dokumentacja), semestr zimowy 2026/27, studia niestacjonarne.
> Temat nr **[XX]**: [tytuł tematu z listy]

## O systemie

[2–4 zdania: jaki problem rozwiązuje system, dla kogo jest i jaka jest jego główna wartość.]

## Zespół

| Osoba         | Login GitHub/GitLab | Rola główna               | Role dodatkowe |
| ------------- | ------------------- | ------------------------- | -------------- |
| Imię Nazwisko | @login              | Kierownik projektu        |                |
| Imię Nazwisko | @login              | Analityk wymagań          |                |
| Imię Nazwisko | @login              | Architekt / projektant BD |                |
| Imię Nazwisko | @login              | Projektant UX/UI          |                |
| Imię Nazwisko | @login              | QA / wdrożenie            |                |

### Macierz odpowiedzialności (RACI)

[Wklejcie i uzupełnijcie tabelę RACI z pliku „role_w_zespole.md”.]

## Dokumentacja

| Nr  | Dokument                                                                             | Właściciel | Status |
| --- | ------------------------------------------------------------------------------------ | ---------- | ------ |
| 00  | [Zarządzanie projektem](docs/00_zarzadzanie.md)                                      |            | ⬜     |
| 01  | [Wizja i zakres](docs/01_wizja_i_zakres.md)                                          |            | ⬜     |
| 02  | [Słownik pojęć](docs/02_slownik.md)                                                  |            | ⬜     |
| 03  | [Wymagania](docs/03_wymagania.md)                                                    |            | ⬜     |
| 04  | [Procesy i przypadki użycia](docs/04_procesy_i_przypadki_uzycia.md)                  |            | ⬜     |
| 05  | [Architektura](docs/05_architektura.md) + [ADR](docs/adr/)                           |            | ⬜     |
| 06  | [Model danych](docs/06_model_danych.md)                                              |            | ⬜     |
| 07  | [Interfejs użytkownika](docs/07_interfejs_uzytkownika.md) + [makiety](docs/makiety/) |            | ⬜     |
| 08  | [Bezpieczeństwo](docs/08_bezpieczenstwo.md)                                          |            | ⬜     |
| 09  | [Wdrożenie](docs/09_wdrozenie.md)                                                    |            | ⬜     |
| 10  | [Testy i jakość](docs/10_testy_i_jakosc.md)                                          |            | ⬜     |
| 11  | [Plan realizacji cz. 2](docs/11_plan_realizacji.md)                                  |            | ⬜     |
| —   | [Macierz śledzenia wymagań](docs/macierz_sledzenia.md)                               |            | ⬜     |

Statusy: ⬜ nie rozpoczęto · 🟨 w trakcie · 🟩 gotowe do recenzji · ✅ zatwierdzone

## Kamienie milowe

| Tag    | Zawartość                                                                                                                                      | Termin | Oddano |
| ------ | ---------------------------------------------------------------------------------------------------------------------------------------------- | ------ | ------ |
| `m1`   | repozytorium i tablica zadań, zespół i RACI, wizja i zakres, interesariusze, rejestr ryzyk, wstępny słownik, ćwiczenie git, pytania do wywiadu |        |        |
| `m2`   | słownik, wymagania WF/WNF z MoSCoW, reguły biznesowe, historyjki z kryteriami akceptacji, C4 kontekst, protokół wywiadu, aktualizacja zakresu  |        |        |
| `m3`   | UC, procesy, model dziedziny, ERD, architektura, ADR, bezpieczeństwo                                                                           |        |        |
| `m4`   | UI, wdrożenie, testy, plan realizacji, macierz śledzenia                                                                                       |        |        |
| `v1.0` | wersja końcowa                                                                                                                                 |        |        |

## Konwencje

Zasady pracy z repozytorium opisuje [CONTRIBUTING.md](CONTRIBUTING.md).

### Identyfikatory artefaktów

| Prefiks | Artefakt                  | Przykład              |
| ------- | ------------------------- | --------------------- |
| `CEL-`  | cel biznesowy             | CEL-01                |
| `INT-`  | interesariusz             | INT-01 Recepcjonistka |
| `RB-`   | reguła biznesowa          | RB-01                 |
| `WF-`   | wymaganie funkcjonalne    | WF-07                 |
| `WNF-`  | wymaganie niefunkcjonalne | WNF-03                |
| `US-`   | historyjka użytkownika    | US-12                 |
| `PB-`   | proces biznesowy          | PB-02                 |
| `UC-`   | przypadek użycia          | UC-05                 |
| `EKR-`  | ekran / makieta           | EKR-04                |
| `ADR-`  | decyzja architektoniczna  | ADR-0003              |
| `TC-`   | przypadek testowy         | TC-21                 |
| `RYZ-`  | ryzyko                    | RYZ-02                |

Identyfikatora raz nadanego **nie zmienia się i nie używa ponownie**. Usunięte wymaganie oznacza się jako ~~wycofane~~.
