# 00. Zarządzanie projektem

## Sposób pracy zespołu

- Kanał komunikacji: Serwer Discord + Google Meets
- Stałe spotkanie zespołu: środa, 11.00
- Tablica zadań: [https://github.com/orgs/PZ-INF-NST-Online-Booking-System/projects/1](https://github.com/orgs/PZ-INF-NST-Online-Booking-System/projects/1)
- Zasada pracy: każde zadanie to Issue z osobą przypisaną i etykietą kamienia (`m1`…`m4`); zmiany wchodzą do `main` wyłącznie przez PR zatwierdzony przez inną osobę ([CONTRIBUTING.md](../CONTRIBUTING.md))
- Przegląd tablicy: raz w tygodniu na spotkaniu zespołu — stan zadań, obciążenie osób, aktualizacja rejestru ryzyk
- Notatki ze spotkań: [`spotkania/`](spotkania/), jeden plik na spotkanie: `RRRR-MM-DD-krotki-opis.md`, np. `2026-11-14-wywiad-z-klientem.md` (uczestnicy, ustalenia, zadania z linkami do Issues)

## Harmonogram semestru

<!-- Tag na gałęzi `main`; liczy się data tagu w repozytorium. -->

| Kamień            | Termin oddania (tag)                   | Odpowiedzialny | Uwagi                                                                                                     |
| ----------------- | -------------------------------------- | -------------- | --------------------------------------------------------------------------------------------------------- |
| M1                | 07.11.2026 (48 h przed zajęciami 2)    | PM             | repozytorium i tablica, zespół i RACI, wizja i zakres, wstępny słownik, ćwiczenie git, pytania do wywiadu |
| M2                | 06.12.2026 (48 h przed zajęciami 3)    | PM             | słownik, wymagania z priorytetami, reguły biznesowe, historyjki, C4 kontekst, protokół wywiadu            |
| M3                | 10.01.2027 (48 h przed zajęciami 4)    | PM             | procesy i UC, model dziedziny, ERD, architektura, ADR, bezpieczeństwo                                     |
| M4                | 31.01.2027 (14 dni przed zajęciami 5)  | PM             | UI i makiety, wdrożenie, testy, plan realizacji cz. 2, macierz śledzenia; po tej dacie recenzja krzyżowa  |
| recenzja krzyżowa | 20.01.2027 — 7 dni przed zajęciami 5   | PM             | Issues z etykietą `recenzja` w repozytorium recenzowanego zespołu                                         |
| v1.0              | 15.02.2027 — razcej już po zajęciach 5 | PM             | wersja końcowa po uwagach z recenzji krzyżowej                                                            |

## Rejestr ryzyk

<!-- Prawdopodobieństwo i wpływ w skali 1–3. Ekspozycja = P × W. -->

| ID     | Ryzyko                                                                                            | P   | W   | P×W | Reakcja (unikanie / łagodzenie / akceptacja)                                                                                    | Właściciel | Status  |
| ------ | ------------------------------------------------------------------------------------------------- | --- | --- | --- | ------------------------------------------------------------------------------------------------------------------------------- | ---------- | ------- |
| RYZ-01 | Członek zespołu nie wywiązuje się z zadań                                                         | 2   | 3   | 6   | łagodzenie: cotygodniowy przegląd tablicy, wczesna eskalacja do prowadzącego                                                    | PM         | otwarte |
| RYZ-02 | Zespół trzyosobowy obsadza pięć rol, osoby łączące dwie role są przeciążone                       | 2   | 2   | 4   | łagodzenie: przegląd obciążenia na spotkaniu tygodniowym; po dojściu czwartej osoby oddzielenie roli UX/UI                      | PM         | otwarte |
| RYZ-03 | Część zespołu nie pracowała wcześniej z gitem i PR — opóźnienia, zmiany wprowadzane poza procesem | 3   | 2   | 6   | łagodzenie: ćwiczenie git w M1, edycja plików przez interfejs GitHuba, instrukcja krok po kroku, recenzja każdego PR przez PM   | PM         | otwarte |
| RYZ-04 | Rozjazd nazewnictwa między dokumentami — to samo pojęcie pod dwiema nazwami                       | 3   | 2   | 6   | łagodzenie: słownik jako jedyne źródło nazw, punkt kontrolny w szablonie PR, macierz śledzenia prowadzona od M2                 | Analityk   | otwarte |
| RYZ-05 | Zakres MVP okazuje się zbyt duży do implementacji w cz. 2                                         | 2   | 3   | 6   | łagodzenie: jawna lista wyłączeń w 1.5, ponowny przegląd zakresu po wywiadzie i przy M4                                         | PM         | otwarte |
| RYZ-06 | Jeden wywiad z klientem o ograniczonym czasie — wymagania pozostają niedoprecyzowane              | 2   | 2   | 4   | łagodzenie: pytania przygotowane i uzgodnione przed zajęciami 2, jawna lista założeń do potwierdzenia, dopytywanie przez Issues | Analityk   | otwarte |
| RYZ-07 | Kumulacja pracy na kilka dni przed terminem kamienia                                              | 3   | 2   | 6   | łagodzenie: Issues z terminem tygodniowym, tag tworzony 48 h przed zajęciami, przegląd tablicy co tydzień                       | PM         | otwarte |
| RYZ-08 | Opóźnienie recenzji krzyżowej po stronie drugiego zespołu                                         | 2   | 2   | 4   | akceptacja: M4 oddane 14 dni przed zajęciami 5, kontakt z zespołem recenzującym od razu po tagu `m4`                            | PM         | otwarte |

## Dziennik decyzji zespołu

| Data           | Decyzja                                                                                                                                                                                                                                                           | Kto podjął                 |
| -------------- | ----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | -------------------------- |
| 2026-10-20     | Zakres MVP ograniczony do systemu dla jednego usługodawcy; wielodostępność, personalizacja wyglądu, widget do osadzania, SMS i integracja z kalendarzem zewnętrznym poza zakresem (uzasadnienie w [01_wizja_i_zakres.md](01_wizja_i_zakres.md#15-zakres-systemu)) | zespół                     |
| 2026-10-20     | Markdown jest jedynym źródłem dokumentacji; diagramy jako kod Mermaid                                                                                                                                                                                             | zespół                     |
| 2026-10-22     | Temat projektu nr 07 z listy: „Gabinet usług (fryzjer / kosmetyczka): rezerwacje wizyt”. Dokumentację odtwarzamy na podstawie działającej aplikacji jednego z członków zespołu, dzięki czemu wymagania opieramy na rzeczywistych rozwiązaniach, a nie na założeniach.                                                                                                                                                                                        | zespół |
| 2026-10-22     | Podział rol przy trzech osobach według doświadczenia, a nie według schematu z materiałów: PM + UX/UI + wdrożenie, Analityk, Architekt/BD + testy i macierz śledzenia (uzasadnienie w [README](../README.md#zespół))                                               | zespół                     |
| 2026-10-29     | Obsługa wielu lokalizacji jednego usługodawcy pozostaje poza zakresem MVP; opis systemu w README doprecyzowany do jednej placówki, żeby zgadzał się z sekcją 1.5. | zespół |
