# 03. Wymagania

## 3.1. Wymagania funkcjonalne

<!-- Priorytet MoSCoW: M (Must), S (Should), C (Could), W (Won't – tym razem nie). Źródło: kto/co zgłosiło wymaganie (INT-xx, wywiad z dnia…). -->

| ID | Wymaganie (System musi/powinien…) | Aktor | Priorytet | Źródło | Historyjki |
|---|---|---|---|---|---|
| WF-01 | System musi umożliwiać Klientowi utworzenie Rezerwacji wolnego Zasobu w wybranym Terminie. | Klient | M | INT-01, wywiad 1 | US-01, US-02 |
| WF-02 | | | | | |

## 3.2. Wymagania niefunkcjonalne

<!-- Każde wymaganie MUSI być mierzalne/weryfikowalne. Kategorie jakości wg ISO/IEC 25010 (wyd. 2023; w nawiasie nazwy z wyd. 2011). Wymagania prawne to ograniczenia spoza modelu jakości – zapisujemy je w tej samej tabeli z kategorią „Ograniczenie prawne”. -->

| ID | Kategoria | Wymaganie | Miara / sposób weryfikacji | Priorytet |
|---|---|---|---|---|
| WNF-01 | Efektywność wydajnościowa | Lista dostępnych Zasobów ładuje się w czasie ≤ 2 s dla 95% żądań przy 50 równoczesnych użytkownikach. | test obciążeniowy | M |
| WNF-02 | Bezpieczeństwo | | | |
| WNF-03 | Zdolność interakcji (użyteczność) | | | |
| WNF-04 | Zdolność interakcji: inkluzywność (dostępność, accessibility) | Interfejs spełnia WCAG 2.2 na poziomie AA. | audyt narzędziem + checklista | S |
| WNF-05 | Niezawodność | | | |
| WNF-06 | Łatwość utrzymania (utrzymywalność) | | | |
| WNF-07 | Ograniczenie prawne (poza ISO 25010) | System przetwarza dane osobowe zgodnie z RODO. | przegląd z checklistą z 08_bezpieczenstwo | M |

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

| ID | Reguła |
|---|---|
| RB-01 | np. Rezerwację można anulować najpóźniej 24 h przed jej rozpoczęciem. |
