# Online Booking System

> Projekt zespołowy systemu informatycznego, cz. 1 (dokumentacja), semestr zimowy 2026/27, studia niestacjonarne.
> Temat nr **07**: Gabinet usług (fryzjer / kosmetyczka): rezerwacje wizyt

## O systemie

System obsługuje zapisy na wizyty u usługodawcy pracującego na terminy — gabinetu, salonu lub konsultanta z obsadą od jednej do kilku osób, w jednej, lub kilku lokalizacjach. Klient wybiera lokalizację/gabinet, usługę, pracownika i wolny termin na publicznej stronie rezerwacji, bez zakładania konta i o dowolnej porze, a system pokazuje wyłącznie terminy faktycznie dostępne, wyklucza kolizje i wysyła potwierdzenie oraz przypomnienie e-mailem. Administrator prowadzi katalog usług, katalog placówek, grafiki pracowników i kartotekę klientów w jednym miejscu, zamiast kalendarza papierowego i zapisów przyjmowanych telefonicznie.

Zakres MVP i świadome wyłączenia opisuje [Wizja i zakres](docs/01_wizja_i_zakres.md#15-zakres-systemu).

## Zespół

| Osoba         | Login GitHub/GitLab | Rola główna               | Role dodatkowe                    |
| ------------- | ------------------- | ------------------------- | --------------------------------- |
| Hubert Pulik  | @hubertPulik        | Kierownik projektu        | Projektant UX/UI, wdrożenie       |
| Imię Nazwisko | @login              | Analityk wymagań          |                                   |
| Imię Nazwisko | @login              | Architekt / projektant BD | Inżynier jakości (testy, macierz) |

Zespół liczy trzy osoby, więc role trzeba łączyć. Zamiast schematu proponowanego dla trzyosobowych zespołów przyjęliśmy podział według doświadczenia: kierownik projektu ma na koncie projektowanie makiet i prototypów oraz wdrożenia produkcyjne, dlatego bierze dodatkowo projektowanie UX/UI i model wdrożenia. Architekt przejmuje testy i macierz śledzenia, bo obie rzeczy opierają się na modelu danych i liście endpointów, które sam projektuje. Analityk prowadzi wymagania w całości i bez obciążenia dodatkową rolą — to najcięższy pojedynczy obszar dokumentacji.

Podział rozkłada też skupiska pracy na kolejne kamienie: M1 i M4 obciążają kierownika projektu, M2 analityka, M3 architekta. Historyjki użytkownika pisze analityk, a przypadki testowe do nich — architekt, więc kryteria akceptacji weryfikuje ktoś inny niż ich autor.

Po dołączeniu czwartej osoby wydzielamy rolę inżyniera jakości (testy, wdrożenie, macierz śledzenia); po piątej — procesy i przypadki użycia przechodzą do drugiego analityka.

### Macierz odpowiedzialności (RACI)

R = wykonuje, A = odpowiada (tylko jedna osoba), C = konsultowany, I = informowany

| Sekcja dokumentacji      | PM + UX/UI + wdrożenie | Analityk | Architekt / BD + testy |
| ------------------------ | ---------------------- | -------- | ---------------------- |
| 00 Zarządzanie projektem | A                      | C        | C                      |
| 01 Wizja i zakres        | A                      | R        | C                      |
| 02 Słownik               | C                      | A        | R                      |
| 03 Wymagania             | R                      | A        | R                      |
| 04 Procesy i UC          | C                      | A        | R                      |
| 05 Architektura          | C                      | C        | A                      |
| 06 Model danych          | I                      | C        | A                      |
| 07 Interfejs użytkownika | A                      | R        | C                      |
| 08 Bezpieczeństwo        | C                      | C        | A                      |
| 09 Wdrożenie             | A                      | I        | C                      |
| 10 Testy                 | C                      | R        | A                      |
| 11 Plan realizacji       | A                      | C        | R                      |
| Macierz śledzenia        | C                      | R        | A                      |

## Dokumentacja

| Nr  | Dokument                                                                             | Właściciel | Status |
| --- | ------------------------------------------------------------------------------------ | ---------- | ------ |
| 00  | [Zarządzanie projektem](docs/00_zarzadzanie.md)                                      | PM         | 🟨     |
| 01  | [Wizja i zakres](docs/01_wizja_i_zakres.md)                                          | PM         | 🟨     |
| 02  | [Słownik pojęć](docs/02_slownik.md)                                                  | Analityk   | ⬜     |
| 03  | [Wymagania](docs/03_wymagania.md)                                                    | Analityk   | ⬜     |
| 04  | [Procesy i przypadki użycia](docs/04_procesy_i_przypadki_uzycia.md)                  | Analityk   | ⬜     |
| 05  | [Architektura](docs/05_architektura.md) + [ADR](docs/adr/)                           | Architekt  | ⬜     |
| 06  | [Model danych](docs/06_model_danych.md)                                              | Architekt  | ⬜     |
| 07  | [Interfejs użytkownika](docs/07_interfejs_uzytkownika.md) + [makiety](docs/makiety/) | PM         | ⬜     |
| 08  | [Bezpieczeństwo](docs/08_bezpieczenstwo.md)                                          | Architekt  | ⬜     |
| 09  | [Wdrożenie](docs/09_wdrozenie.md)                                                    | PM         | ⬜     |
| 10  | [Testy i jakość](docs/10_testy_i_jakosc.md)                                          | Architekt  | ⬜     |
| 11  | [Plan realizacji cz. 2](docs/11_plan_realizacji.md)                                  | PM         | ⬜     |
| —   | [Macierz śledzenia wymagań](docs/macierz_sledzenia.md)                               | Architekt  | ⬜     |

Statusy: ⬜ nie rozpoczęto · 🟨 w trakcie · 🟩 gotowe do recenzji · ✅ zatwierdzone

## Kamienie milowe

| Tag    | Zawartość                                                                                                                                     | Termin     | Oddano |
| ------ | --------------------------------------------------------------------------------------------------------------------------------------------- | ---------- | ------ |
| `m1`   | repozytorium i tablica zadań, zespół i RACI,wizja i zakres, interesariusze, rejestr ryzyk, wstępny słownik, ćwiczenie git, pytania do wywiadu | 07.11.2026 |        |
| `m2`   | słownik, wymagania WF/WNF z MoSCoW, reguły biznesowe, historyjki z kryteriami akceptacji, C4 kontekst, protokół wywiadu, aktualizacja zakresu | 06.12.2026 |        |
| `m3`   | UC, procesy, model dziedziny, ERD, architektura, ADR, bezpieczeństwo                                                                          | 10.01.2027 |        |
| `m4`   | UI, wdrożenie, testy, plan realizacji, macierz śledzenia                                                                                      | 31.01.2027 |        |
| `v1.0` | wersja końcowa                                                                                                                                | 15.02.2027 |        |

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
