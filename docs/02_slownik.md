# 02. Słownik pojęć dziedziny

<!--
Zasady:
- Jedno pojęcie, jedna nazwa. Synonimy wpisujemy w osobnej kolumnie i NIE używamy ich w dokumentacji.
- Definicja w języku klienta, bez żargonu technicznego.
- Nazwa angielska posłuży w cz. 2 jako nazwa klasy/tabeli.
- Kolejność alfabetyczna.
-->

| Pojęcie | Nazwa ang. (dla kodu) | Definicja | Synonimy (niezalecane) | Przykład | Powiązane pojęcia |
|---|---|---|---|---|---|
| Rezerwacja | Reservation | Zarezerwowanie przez Klienta konkretnego Zasobu na określony Termin. Rezerwacja ma Status. | booking, zapis | Rezerwacja sali 2.14 na 12.11, 10:00–12:00 | Klient, Zasób, Termin, Status rezerwacji |
| | | | | | |

## Wartości wyliczeniowe

<!-- Słowniki wartości: statusy, typy, kategorie. Przydadzą się w modelu danych. -->

### Status rezerwacji

| Wartość | Znaczenie |
|---|---|
| NOWA | |
| POTWIERDZONA | |
| ANULOWANA | |
| ZREALIZOWANA | |
