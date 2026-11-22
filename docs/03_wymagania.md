# 03. Wymagania

## 3.1. Wymagania funkcjonalne

<!-- Priorytet MoSCoW: M (Must), S (Should), C (Could), W (Won't - tym razem nie). Źródło: kto/co zgłosiło wymaganie (INT-xx, wywiad z dnia 2026-11-21: U-xx ustalenie, S-xx kwestia otwarta, karta Z-01). -->

| ID    | Wymaganie (System musi/powinien…)                                                                                                                                                                                                                                            | Aktor                    | Priorytet | Źródło                        | Historyjki |
| ----- | ---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | ------------------------ | --------- | ----------------------------- | ---------- |
| WF-01 | System musi umożliwiać Klientowi rezerwację wybranej Usługi u wybranego Pracownika w Wolnym terminie, bez zakładania konta. Rezerwacja ma od razu status POTWIERDZONA, bez akceptacji przez Usługodawcę.                                                                     | Klient                   | M         | INT-03, wywiad U-07, U-28     | US-01      |
| WF-02 | System powinien pozwalać Klientowi wybrać opcję „dowolny Pracownik” i przydzielać Rezerwację wolnemu Pracownikowi, przy czym właścicielka jest wybierana jako ostatnia w kolejności.                                                                                         | Klient                   | S         | wywiad U-12                   | US-02      |
| WF-03 | System musi wyznaczać Wolne terminy na podstawie Grafiku dostępności Pracownika, czasu trwania Usługi, Czasu buforowego danej Usługi, istniejących Rezerwacji, Horyzontu rezerwacji i Minimalnego wyprzedzenia oraz pokazywać na stronie wyłącznie terminy faktycznie wolne. | System                   | M         | wywiad U-09, U-10, U-11, U-28 | US-03      |
| WF-04 | System musi uniemożliwiać utworzenie dwóch Rezerwacji tego samego Pracownika na zachodzące na siebie Terminy.                                                                                                                                                                | System                   | M         | INT-01, wywiad U-05           | US-04      |
| WF-05 | System musi wymagać przy Rezerwacji imienia, nazwiska, numeru telefonu i adresu e-mail oraz zgody na przetwarzanie danych, a nie zbierać adresu zamieszkania ani daty urodzenia. Przy Rezerwacji założonej przez Administratora adres e-mail jest opcjonalny (WF-06).        | Klient                   | M         | wywiad U-14                   | US-05      |
| WF-06 | System musi umożliwiać Administratorowi założenie Rezerwacji w imieniu Klienta, który zadzwonił, także gdy Klient nie ma adresu e-mail. Taki Klient dostaje Powiadomienia SMS-em.                                                                                            | Administrator            | M         | wywiad U-22, U-23, S-08       | US-06      |
| WF-07 | System musi umożliwiać Klientowi anulowanie Rezerwacji Linkiem do anulowania najpóźniej 24 godziny przed Terminem (Reguła anulowania).                                                                                                                                       | Klient                   | M         | INT-03, wywiad U-15           | US-07      |
| WF-08 | System musi umożliwiać Administratorowi anulowanie Rezerwacji po upływie Reguły anulowania, gdy Klient odwoła ją telefonicznie. Taka Rezerwacja dostaje status ANULOWANA, a nie NIEOBECNA.                                                                                   | Administrator            | M         | wywiad U-15, U-16             | US-08      |
| WF-09 | System musi umożliwiać Administratorowi oznaczenie Nieobecności Klienta po upływie Terminu (status NIEOBECNA) i zapisywać ją w Kartotece klientów.                                                                                                                           | Administrator            | M         | wywiad U-16, U-17             | US-09      |
| WF-10 | System musi blokować samodzielną rezerwację na stronie dla Klienta, który ma dwie Nieobecności. Taki Klient może się umówić tylko przez Administratora.                                                                                                                      | System                   | M         | wywiad U-17, S-01             | US-10      |
| WF-11 | System powinien nie pozwalać zapisać Klienta na Usługę wymagającą Konsultacji, dopóki Klient nie odbył Konsultacji. Konsultacja jest Usługą o czasie 15 minut i cenie 0 zł.                                                                                                  | Klient                   | S         | wywiad U-08, S-07             | US-11      |
| WF-12 | System musi umożliwiać Administratorowi prowadzenie katalogu Usług: nazwa, opis, czas trwania, cena, Czas buforowy i lista Pracowników wykonujących Usługę.                                                                                                                  | Administrator            | M         | INT-01, wywiad U-11, U-29     | US-12      |
| WF-13 | System musi umożliwiać Administratorowi ustalanie Grafiku dostępności Pracownika (stała podstawa tygodniowa), dodawanie Wyjątków w grafiku i Dni wolnych oraz odwołanie całego dnia Pracownika także w trakcie dnia. Wolne terminy tego dnia od razu znikają ze strony.      | Administrator            | M         | wywiad U-13                   | US-13      |
| WF-14 | System musi pokazywać Administratorowi jeden kalendarz Rezerwacji całego Usługodawcy, ze wszystkimi Pracownikami.                                                                                                                                                            | Administrator            | M         | INT-01, wywiad U-01           | US-14      |
| WF-15 | System musi pokazywać zalogowanemu Pracownikowi jego własny dzień z Rezerwacjami, numerem telefonu Klienta i notatkami o Kliencie. Pracownik nie widzi cennika i nie edytuje Grafików dostępności.                                                                           | Pracownik                | M         | INT-02, wywiad U-21           | US-15      |
| WF-16 | System musi prowadzić Kartotekę klientów: dane kontaktowe, listę Rezerwacji, Nieobecności i notatki o Kliencie (numer farby, utleniacz, czas). Notatki widzi Administrator i Pracownik.                                                                                      | Administrator, Pracownik | M         | wywiad U-18, S-01             | US-16      |
| WF-17 | System musi pokazywać Pracownikowi uczulenia i choroby skóry Klienta jako osobny znacznik (ikona, np. pigułka) z podpowiedzią po najechaniu, przy Rezerwacji i w Kartotece klientów.                                                                                         | Pracownik                | M         | wywiad U-20, S-01             | US-17      |
| WF-18 | System musi wysyłać Klientowi e-mailem Powiadomienia: potwierdzenie Rezerwacji, Przypomnienie przed Terminem i informację o Anulowaniu rezerwacji.                                                                                                                           | System                   | M         | INT-03, wywiad U-24, U-25     | US-18      |
| WF-19 | System musi wysyłać Powiadomienia także SMS-em i pozwalać wybrać Kanał powiadomienia dla każdego typu Powiadomienia. Klient bez adresu e-mail dostaje potwierdzenie i Przypomnienie SMS-em.                                                                                  | System                   | M         | wywiad U-24, U-25, S-08       | US-19      |
| WF-20 | System powinien pokazywać Administratorowi przy Rezerwacji, że wysyłka Powiadomienia się nie udała, żeby mógł zadzwonić do Klienta.                                                                                                                                          | Administrator            | S         | wywiad U-26                   | US-20      |
| WF-21 | System powinien pozwalać Administratorowi oznaczyć przy Rezerwacji, że zadatek został przyjęty poza systemem.                                                                                                                                                                | Administrator            | S         | wywiad S-09                   | US-21      |
| WF-22 | System musi umożliwiać Administratorowi i Pracownikowi logowanie, zmianę i reset hasła. Klient rezerwuje bez konta.                                                                                                                                                          | Administrator, Pracownik | M         | INT-01, INT-02, 1.5           | US-22      |
| WF-23 | System w tej wersji nie będzie przyjmował płatności ani zadatków online przy Rezerwacji.                                                                                                                                                                                     | Klient                   | W         | karta Z-01, wywiad S-06       | -          |
| WF-24 | System w tej wersji nie będzie obsługiwał wielu lokalizacji jednego Usługodawcy.                                                                                                                                                                                             | Administrator            | W         | wywiad U-06                   | -          |

## 3.2. Wymagania niefunkcjonalne

<!-- Każde wymaganie MUSI być mierzalne/weryfikowalne. Kategorie jakości wg ISO/IEC 25010 (wyd. 2023; w nawiasie nazwy z wyd. 2011). Wymagania prawne to ograniczenia spoza modelu jakości – zapisujemy je w tej samej tabeli z kategorią „Ograniczenie prawne”. -->

| ID     | Kategoria                                                     | Wymaganie                                                                                             | Miara / sposób weryfikacji                | Priorytet |
| ------ | ------------------------------------------------------------- | ----------------------------------------------------------------------------------------------------- | ----------------------------------------- | --------- |
| WNF-01 | Efektywność wydajnościowa                                     | Lista dostępnych Zasobów ładuje się w czasie ≤ 2 s dla 95% żądań przy 50 równoczesnych użytkownikach. | test obciążeniowy                         | M         |
| WNF-02 | Bezpieczeństwo                                                |                                                                                                       |                                           |           |
| WNF-03 | Zdolność interakcji (użyteczność)                             |                                                                                                       |                                           |           |
| WNF-04 | Zdolność interakcji: inkluzywność (dostępność, accessibility) | Interfejs spełnia WCAG 2.2 na poziomie AA.                                                            | audyt narzędziem + checklista             | S         |
| WNF-05 | Niezawodność                                                  |                                                                                                       |                                           |           |
| WNF-06 | Łatwość utrzymania (utrzymywalność)                           |                                                                                                       |                                           |           |
| WNF-07 | Ograniczenie prawne (poza ISO 25010)                          | System przetwarza dane osobowe zgodnie z RODO.                                                        | przegląd z checklistą z 08_bezpieczenstwo | M         |

## 3.3. Historyjki użytkownika

<!--
Format: Jako <aktor> chcę <cel>, aby <korzyść>.
Kryteria akceptacji w formacie Given/When/Then (Zakładając/Gdy/Wtedy). Min. 2 kryteria na historyjkę, w tym 1 scenariusz błędny.
Historyjka spełnia INVEST.
-->

### US-01: Rezerwacja wolnego zasobu

**Jako** Klient **chcę** zarezerwować wolną salę w wybranym terminie, **aby** mieć pewność, że będzie dostępna na moje zajęcia.

- Wymaganie: WF-01 · Priorytet: M · Szacunek: [punkty / S-M-L]

**Kryteria akceptacji:**

```gherkin
Scenariusz: Udana rezerwacja
  Zakładając że jestem zalogowanym Klientem
  I sala 2.14 jest wolna 12.11 w godz. 10:00–12:00
  Gdy wybiorę tę salę i ten termin i potwierdzę rezerwację
  Wtedy rezerwacja otrzyma status POTWIERDZONA
  I otrzymam e-mail z potwierdzeniem

Scenariusz: Termin zajęty
  Zakładając że sala 2.14 jest zajęta 12.11 w godz. 11:00–13:00
  Gdy spróbuję zarezerwować ją na 10:00–12:00
  Wtedy zobaczę komunikat o kolizji terminów
  I rezerwacja nie zostanie utworzona
```

### US-02: …

## 3.4. Reguły biznesowe

| ID    | Reguła                                                                |
| ----- | --------------------------------------------------------------------- |
| RB-01 | np. Rezerwację można anulować najpóźniej 24 h przed jej rozpoczęciem. |
