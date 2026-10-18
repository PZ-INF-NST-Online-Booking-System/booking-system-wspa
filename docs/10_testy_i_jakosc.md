# 10. Testy i zapewnienie jakości

## 10.1. Strategia testów

| Poziom | Co testujemy | Narzędzie (propozycja) | Kto | Kiedy |
|---|---|---|---|---|
| Jednostkowe | logika domenowa (reguły RB-xx) | np. JUnit / xUnit / pytest / Vitest | programiści | przy każdej zmianie kodu |
| Integracyjne | API + baza danych | np. Testcontainers, Postman/Newman | programiści | przed scaleniem PR/MR |
| E2E / systemowe | kluczowe ścieżki UI | np. Playwright / Cypress | QA | przed wydaniem |
| Akceptacyjne | kryteria akceptacji US | scenariusze Given/When/Then | QA + klient | odbiór |
| Niefunkcjonalne | WNF (wydajność, bezpieczeństwo, dostępność) | np. k6, OWASP ZAP, axe/Lighthouse | QA | przed wydaniem |

## 10.2. Wczesne wykrywanie błędów (shift-left)

<!-- Opiszcie, które praktyki stosujecie i jak: przegląd wymagań, recenzje PR, lintery, analiza statyczna (np. SonarQube), TDD/BDD, Definition of Done. -->

### Definition of Done (dla cz. 2)

- [ ] Kod przeszedł recenzję (min. 1 osoba)
- [ ] Testy jednostkowe dla nowej logiki, pokrycie ≥ …%
- [ ] Kryteria akceptacji historyjki zweryfikowane
- [ ] Wszystkie testy automatyczne przechodzą
- [ ] Dokumentacja zaktualizowana

## 10.3. Kryteria wejścia/wyjścia i środowisko testowe

## 10.4. Przypadki testowe

<!-- Min. 1 przypadek testowy na każde wymaganie z priorytetem M. Wyprowadzane z kryteriów akceptacji. -->

### TC-01: Utworzenie rezerwacji w wolnym terminie

| Pole | Wartość |
|---|---|
| Powiązanie | US-01, WF-01, UC-01 |
| Poziom | E2E |
| Warunki wstępne | Klient zalogowany; sala 2.14 wolna 12.11 10:00–12:00 |
| Dane testowe | sala 2.14; 12.11; 10:00–12:00 |

| Krok | Akcja | Oczekiwany rezultat |
|---|---|---|
| 1 | Otwórz EKR-04 „Nowa rezerwacja” | formularz pusty, przycisk nieaktywny |
| 2 | Wybierz salę i termin | przycisk aktywny |
| 3 | Kliknij „Zarezerwuj” | komunikat sukcesu; rezerwacja widoczna w EKR-05 ze statusem POTWIERDZONA |

### TC-02: Próba rezerwacji w zajętym terminie

…

## 10.5. Zarządzanie defektami

<!-- Gdzie zgłaszane (Issues z etykietą bug), szablon zgłoszenia, klasyfikacja ważności (krytyczny/wysoki/średni/niski). -->
