# Macierz śledzenia wymagań

<!--
Każde wymaganie funkcjonalne z priorytetem M musi mieć: co najmniej jedną historyjkę, przypadek użycia lub proces, ekran (jeśli dotyczy UI) i przypadek testowy.
Puste pole = luka w dokumentacji (do uzupełnienia albo uzasadnienia w kolumnie Uwagi).
-->

| Wymaganie | Priorytet | Historyjki | UC / PB | Ekrany | Tabele / encje | Endpointy API | Testy | Uwagi |
|---|---|---|---|---|---|---|---|---|
| WF-01 | M | US-01 | UC-01, PB-01 | EKR-04 | reservation, resource | POST /api/reservations | TC-01, TC-02 | |
| WNF-01 | M | — | — | EKR-03 | — | GET /api/resources | TC-30 (test obciążeniowy) | |
