# 09. Model wdrożenia

## 9.1. Środowiska

| Środowisko | Przeznaczenie | Gdzie | Dane |
|---|---|---|---|
| dev | praca programistów | lokalnie (Docker Compose) | dane testowe |
| test/staging | testy akceptacyjne | np. darmowy hosting / serwer uczelni | dane testowe |
| prod | użytkownicy | | dane rzeczywiste |

## 9.2. Diagram wdrożenia

```mermaid
flowchart TB
    subgraph Klient["Urządzenie użytkownika"]
        B[Przeglądarka]
    end
    subgraph Serwer["Serwer VPS / chmura (Linux)"]
        RP[Reverse proxy<br/>nginx + TLS]
        subgraph Docker["Docker Compose"]
            FE[Kontener: frontend]
            BE[Kontener: backend API]
            DB[(Kontener: PostgreSQL<br/>wolumen danych)]
        end
    end
    B -->|HTTPS 443| RP
    RP --> FE
    RP -->|/api| BE
    BE -->|5432| DB
```

## 9.3. Potok CI/CD (opcjonalnie)

<!-- Sekcja NIEOBOWIĄZKOWA. Jeśli zespół chce, może naszkicować automatyzację budowania, testów i wdrożenia (np. GitHub Actions / GitLab CI). Jeśli nie – usuńcie tę sekcję, a procedurę budowania i uruchomienia opiszcie krótko w 9.5. -->

```mermaid
flowchart LR
    P[push / PR] --> L[lint + build] --> T[testy jednostkowe i integracyjne] --> S[analiza statyczna + skan zależności] --> I[obraz Docker] --> D[deploy na staging] --> A[testy E2E / akceptacyjne] --> R[ręczne zatwierdzenie] --> PR[deploy na prod]
```

## 9.4. Konfiguracja i sekrety

<!-- Zmienne środowiskowe, gdzie przechowywane sekrety (np. plik `.env` poza repozytorium), czego nie commitujemy. -->

## 9.5. Plan wdrożenia u klienta

| Krok | Opis | Odpowiedzialny |
|---|---|---|
| 1 | Przygotowanie infrastruktury | |
| 2 | Migracja / import danych początkowych | |
| 3 | Szkolenie użytkowników | |
| 4 | Uruchomienie pilotażowe | |
| 5 | Odbiór (testy akceptacyjne klienta) | |

## 9.6. Kopie zapasowe, monitoring, utrzymanie

- Backup: częstotliwość, retencja, test odtworzenia …
- Monitoring i logi: …
- Procedura wycofania wersji (rollback): …
