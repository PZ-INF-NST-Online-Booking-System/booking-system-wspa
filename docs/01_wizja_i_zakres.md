# 01. Wizja i zakres systemu

## 1.1. Opis problemu

| | |
|---|---|
| **Problem** | Zapisy na wizyty przyjmowane są telefonicznie i w wiadomościach, a grafik pracowników prowadzony jest w kalendarzu papierowym albo arkuszu kalkulacyjnym. |
| **dotyczy** | małych usługodawców pracujących na wizyty (gabinety, salony, konsultanci) z obsadą od jednej do kilku osób oraz ich klientów |
| **skutkiem jest** | przerywanie pracy telefonami, możliwość zapisu wyłącznie w godzinach otwarcia, dwie rezerwacje na ten sam termin, nieobecności klientów, którzy zapomnieli o wizycie, oraz brak wiarygodnej historii zapisów |
| **dobre rozwiązanie** | klient rezerwuje sam, o dowolnej porze, widząc wyłącznie terminy faktycznie wolne; system pilnuje kolizji, potwierdza rezerwację i przypomina o wizycie e-mailem, a usługodawca prowadzi jeden grafik dla całego zespołu |

## 1.2. Cel biznesowy i mierniki sukcesu

<!-- Cele mierzalne (SMART), np. „skrócenie czasu obsługi rezerwacji z 10 do 3 minut”.
Wartości docelowe i dane bazowe (obecny odsetek nieobecności, liczba telefonów dziennie) wymagają potwierdzenia w wywiadzie z klientem na zajęciach 2. -->

| ID     | Cel                                                          | Miernik                                                                            | Wartość docelowa                                       |
| ------ | ------------------------------------------------------------ | ---------------------------------------------------------------------------------- | ------------------------------------------------------ |
| CEL-01 | Przeniesienie zapisów z rozmów telefonicznych do samoobsługi | udział rezerwacji założonych samodzielnie przez klienta we wszystkich rezerwacjach | ≥ 70% w trzecim miesiącu po wdrożeniu                  |
| CEL-02 | Skrócenie czasu potrzebnego na zapisanie się na wizytę       | mediana czasu od otwarcia strony rezerwacji do potwierdzenia rezerwacji            | ≤ 2 minuty                                             |
| CEL-03 | Wyeliminowanie dwóch rezerwacji na ten sam termin            | liczba kolizji terminów zgłoszonych w kwartale                                     | 0                                                      |
| CEL-04 | Ograniczenie nieobecności klientów na wizytach               | udział wizyt niezrealizowanych bez wcześniejszego anulowania                       | ≤ 10% (przy przypomnieniu wysyłanym 24 h przed wizytą) |
| CEL-05 | Umożliwienie zapisu poza godzinami pracy usługodawcy         | udział rezerwacji złożonych poza godzinami otwarcia                                | ≥ 30%                                                  |

## 1.3. Interesariusze

| ID | Interesariusz | Opis / rola | Oczekiwania wobec systemu | Wpływ (W/Ś/N) | Zainteresowanie (W/Ś/N) |
|---|---|---|---|---|---|
| INT-01 | | | | | |

## 1.4. Użytkownicy systemu (aktorzy)

| Aktor | Kim jest | Jak często korzysta | Kompetencje cyfrowe |
|---|---|---|---|
| | | | |

## 1.5. Zakres systemu

### W zakresie (MVP — realizacja w cz. 2)

- **Katalog usług** — nazwa, opis, czas trwania, cena, wskazanie pracowników, którzy wykonują daną usługę.
- **Pracownicy i grafik dostępności** — godziny pracy w tygodniu, wyjątki jednorazowe dla wybranej daty, dni wolne.
- **Publiczna strona rezerwacji** — wybór usługi, pracownika i wolnego terminu, formularz danych klienta ze zgodą na przetwarzanie danych.
- **Wyznaczanie wolnych terminów** — na podstawie grafiku pracownika, czasu trwania usługi, czasu buforowego i istniejących rezerwacji.
- **Rezerwacja i jej cykl życia** — statusy potwierdzona, zrealizowana, anulowana; zabezpieczenie przed dwiema rezerwacjami na ten sam termin.
- **Anulowanie przez klienta** — linkiem z jednorazowym tokenem, bez zakładania konta, w granicach reguły czasowej ustalonej przez usługodawcę.
- **Powiadomienia e-mail** — potwierdzenie rezerwacji, przypomnienie przed wizytą, informacja o anulowaniu; treści ze szablonów z miejscami na dane.
- **Panel administracyjny** — kalendarz rezerwacji, kartoteka klientów, zarządzanie usługami, pracownikami i grafikami, konfiguracja systemu (strefa czasowa, długość kroku terminu, czas buforowy, horyzont rezerwacji, reguła anulowania).
- **Konta i role** — administrator i pracownik: logowanie, zmiana i reset hasła. Klient rezerwuje bez konta.

### Poza zakresem (świadomie wyłączone)

- **Obsługa wielu niezależnych usługodawców w jednej instancji** — model danych to przewiduje (patrz ADR), ale panel operatora i izolacja danych między usługodawcami to zakres osobnego projektu.
- **Personalizacja wyglądu pod markę usługodawcy** (kolory, logo, czcionki) — nie wpływa na żaden z celów CEL-01…CEL-05.
- **Widget do osadzania na obcej stronie** — tę samą potrzebę zaspokaja publiczna strona rezerwacji w ramach aplikacji.
- **Powiadomienia SMS** — wymagają płatnej usługi zewnętrznej; e-mail wystarcza do realizacji CEL-04.
- **Synchronizacja z zewnętrznym kalendarzem** (np. Google Calendar).
- **Wiele lokalizacji jednego usługodawcy.**
- **Usługi zdalne z linkiem do spotkania online.**
- **Płatności i zadatki online.**
- **Rezerwacje cykliczne i pakiety wizyt.**
- **Lista rezerwowa na zajęty termin.**
- **Konto klienta z historią wizyt** — dane klienta prowadzi usługodawca w kartotece.
- **Aplikacja mobilna** — strona rezerwacji działa responsywnie w przeglądarce.

### Możliwe rozszerzenia (po MVP)

Kolejność wynika z wpływu na cele biznesowe:

1. Konto klienta z historią wizyt i samoobsługową zmianą terminu.
2. Obsługa wielu usługodawców w jednej instancji wraz z personalizacją wyglądu.
3. Powiadomienia SMS jako kanał uzupełniający przypomnienia.
4. Synchronizacja grafiku z zewnętrznym kalendarzem pracownika.
5. Widget do osadzania na stronie usługodawcy.
6. Płatności i zadatki online, lista rezerwowa, rezerwacje cykliczne.

## 1.6. Kontekst i systemy zewnętrzne

<!-- Z jakimi systemami zewnętrznymi system współpracuje (poczta e-mail, bramka płatności, mapy, logowanie przez Google…)? -->

## 1.7. Założenia i ograniczenia

| Typ | Opis |
|---|---|
| Założenie | np. użytkownicy mają dostęp do Internetu i przeglądarki |
| Ograniczenie | np. budżet: wyłącznie darmowe/otwarte technologie; realizacja w 1 semestr przez zespół N-osobowy |

## 1.8. Rozwiązania konkurencyjne / analiza istniejących narzędzi

| Rozwiązanie | Co robi dobrze | Czego brakuje | Wniosek dla naszego projektu |
|---|---|---|---|
| | | | |
