# Wywiad z klientem - przygotowanie

- **Data:** 2026-11-09 (zajęcia 2)
- **Klient:** prowadzący w roli właściciela firmy usługowej zamawiającego system (INT-01, INT-05)
- **Zespół:** Hubert Pulik, Aneta Waśko, Hanna Yablonska

## Cel wywiadu

1. Poznać, jak Usługodawca dziś przyjmuje Rezerwacje i co mu w tym najbardziej przeszkadza.
2. Potwierdzić albo poprawić zakres MVP z sekcji [1.5](../01_wizja_i_zakres.md#15-zakres-systemu) oraz założenia z sekcji [1.7](../01_wizja_i_zakres.md#17-założenia-i-ograniczenia).
3. Ustalić reguły rezerwacji i anulowania, potrzebne do wymagań i reguł biznesowych w M2.
4. Zebrać wartości bazowe do celów CEL-01...CEL-05 z sekcji [1.2](../01_wizja_i_zakres.md#12-cel-biznesowy-i-mierniki-sukcesu).

## Role podczas wywiadu

| Osoba | Zadanie |
|---|---|
| Aneta Waśko | prowadzi rozmowę i zadaje pytania z listy |
| Hubert Pulik | notuje odpowiedzi i ustalenia, dopytuje o zakres i priorytety |
| Hanna Yablonska | pilnuje czasu, dopytuje o szczegóły dotyczące danych i poczty e-mail |

Zasada: pytania oznaczone **(TL)** muszą paść. Jeśli brakuje czasu, pomijamy pytania z grupy G, a nie z grup B-D.

## Założenia do potwierdzenia

| Nr | Założenie | Skąd | Pytanie |
|---|---|---|---|
| Z-01 | Klient rezerwuje bez zakładania konta. | 1.5 | B6 |
| Z-02 | Rezerwacja jest potwierdzona od razu, bez akceptacji przez Usługodawcę. | 1.5, 02 Status rezerwacji | B1 |
| Z-03 | Powiadomienia wysyłamy tylko e-mailem, bez SMS. | 1.5 | F1 |
| Z-04 | Przypomnienie wysyłamy 24 godziny przed Terminem. | 1.2 CEL-04 | F2 |
| Z-05 | Usługodawca ma jedną lokalizację. | 1.5 | A5 |
| Z-06 | Osoba na recepcji korzysta z roli Administrator. | 1.4 | E2 |
| Z-07 | Usługodawca przekaże dane początkowe (Usługi, ceny, Pracownicy, Grafiki dostępności) i będzie je aktualizować. | 1.7 | G3 |
| Z-08 | Wartości bazowe celów (obecna liczba telefonów, odsetek nieobecności, liczba kolizji) są do ustalenia; bez nich nie da się ocenić CEL-01...CEL-05. | 1.2 | A2, A3, A4 |

## Pytania

### A. Obecny sposób pracy i jego bolączki

1. Jak dziś wygląda droga Klienta od pomysłu „umówię się” do wpisu w grafiku? (→ 1.1)
2. Ile telefonów i wiadomości w sprawie Rezerwacji odbieracie w typowym dniu i kto je odbiera, gdy wszyscy pracują z Klientami? (→ 1.2 CEL-01)
3. Co się dzieje dziś, kiedy Klient nie przyjdzie na umówioną wizytę? Jak często to się zdarza? (→ 1.2 CEL-04)
4. Proszę opisać ostatnią sytuację, w której dwie osoby zostały zapisane na ten sam Termin. Jak to wyszło na jaw i jak to rozwiązaliście? (→ 1.2 CEL-03)
5. **(TL)** Czy w MVP potrzebna jest obsługa więcej niż jednej lokalizacji? (→ 1.5)

### B. Reguły rezerwacji

1. **(TL)** Czy Rezerwacja jest potwierdzona od razu, czy ktoś musi ją zaakceptować? (→ 02 Status rezerwacji)
2. **(TL)** Na ile dni w przód można się zapisać i jakie jest minimalne wyprzedzenie? (→ 02 Horyzont rezerwacji)
3. **(TL)** Czy między wizytami potrzebna jest przerwa i czy zależy od rodzaju Usługi? (→ 02 Czas buforowy)
4. Jak Klient wybiera dziś Pracownika? Co ma się stać, gdy Klientowi jest obojętne, kto wykona Usługę? (→ 1.5 Publiczna strona rezerwacji)
5. Jak zmieniają się godziny pracy Pracowników w ciągu miesiąca i kto o tym decyduje? (→ 02 Grafik dostępności, Wyjątek w grafiku)
6. Jakie dane musicie dostać od Klienta przy zapisie, a o jakie nie chcecie go pytać? (→ 1.5, 08)

### C. Anulowanie i nieobecności

1. **(TL)** Do kiedy Klient może odwołać wizytę samodzielnie? (→ 02 Reguła anulowania)
2. **(TL)** Czy Klient może przenieść wizytę na inny termin, czy musi odwołać i zapisać się ponownie? (→ 1.5 rozszerzenia)
3. Co ma się dziać, gdy Klient chce odwołać wizytę po upływie tego czasu? (→ 02 Reguła anulowania)
4. Jak chcecie odróżniać Klientów, którzy nie przyszli, od tych, którzy przyszli? Do czego ta informacja byłaby potrzebna? (→ 02 Status rezerwacji ZREALIZOWANA)

### D. Dane klientów i ich ochrona

1. **(TL)** Jak długo przechowujecie dane Klientów po ostatniej wizycie? (→ 08, 1.7)
2. Co dziś robicie, gdy Klient prosi o usunięcie swoich danych? (→ 08, INT-06)
3. Jakie informacje o Klientach zapisujecie dziś poza imieniem i kontaktem i do czego ich używacie? (→ 02 Kartoteka klientów)

### E. Role i uprawnienia

1. **(TL)** Czy Pracownik loguje się do systemu, czy grafik prowadzi wyłącznie Administrator? (→ 1.4)
2. Kto dziś odbiera telefony i zapisuje Klientów? Czy ta osoba powinna mieć te same możliwości co właściciel, np. zmianę cennika i Grafików dostępności? (→ 1.4, Z-06)
3. **(TL)** Czy Pracownik ma widzieć dane kontaktowe Klienta i notatki o nim? (→ 08)
4. Jak ma wyglądać zapis Klienta, który dzwoni zamiast rezerwować przez stronę? (→ 1.5 Panel administracyjny)

### F. Powiadomienia

1. Jakimi kanałami kontaktujecie się dziś z Klientami i który z nich Klienci odczytują najszybciej? (→ 1.5, Z-03)
2. Kiedy przypomnienie o wizycie ma realnie szansę zapobiec nieobecności: dzień wcześniej, kilka godzin wcześniej? (→ 1.2 CEL-04)
3. Co ma się stać, gdy Klient nie dostanie potwierdzenia, bo wiadomość nie dotarła? Kto i skąd ma się o tym dowiedzieć? (→ 1.6.1)

### G. Priorytety i kryteria odbioru

1. Po czym po trzech miesiącach od wdrożenia poznacie, że system się sprawdził? (→ 1.2)
2. Bez której funkcji system nie miałby dla Was sensu, a z której moglibyście zrezygnować w pierwszej wersji? (→ 1.5)
3. Kto przygotuje listę Usług, cen i godzin pracy przed uruchomieniem i jak często te dane się zmieniają? (→ 1.7, Z-07)

## Notatki z wywiadu (uzupełniamy po zajęciach 2)

### Odpowiedzi

| Pytanie | Odpowiedź klienta | Wpływ na dokumentację |
|---|---|---|
| | | |

### Potwierdzone i odrzucone założenia

| Nr | Potwierdzone / odrzucone | Uwagi |
|---|---|---|
| | | |

### Nowe ustalenia i otwarte sprawy

-

### Zadania po wywiadzie

-
