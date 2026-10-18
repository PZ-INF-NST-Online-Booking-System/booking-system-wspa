# 04. Procesy i przypadki użycia

## 4.1. Procesy biznesowe

<!-- 2–4 najważniejsze procesy. Diagram aktywności z torami (subgraph = tor/aktor). -->

### PB-01: [Nazwa procesu, np. Obsługa rezerwacji]

- Zdarzenie inicjujące: …
- Rezultat: …
- Uczestnicy: …

```mermaid
flowchart TD
    subgraph Klient
        A([Start]) --> B[Wybiera zasób i termin]
        B --> C[Potwierdza rezerwację]
    end
    subgraph System
        C --> D{Termin wolny?}
        D -- tak --> E[Zapisuje rezerwację]
        E --> F[Wysyła e-mail z potwierdzeniem]
        D -- nie --> G[Wyświetla komunikat o kolizji]
        G --> B
    end
    F --> H([Koniec])
```

## 4.2. Diagram przypadków użycia

<!--
Mermaid nie ma natywnego diagramu UC – stosujemy flowchart z konwencją:
aktor = węzeł ((nazwa)), przypadek użycia = węzeł ([UC-xx nazwa]), granica systemu = subgraph.
Alternatywnie PlantUML (renderowany w GitLab; na GitHub – jako obraz wygenerowany z pliku .puml).
-->

```mermaid
flowchart LR
    K((Klient))
    A((Administrator))
    subgraph System rezerwacji
        UC1([UC-01 Zarezerwuj zasób])
        UC2([UC-02 Anuluj rezerwację])
        UC3([UC-03 Zarządzaj zasobami])
        UC4([UC-04 Przeglądaj zasoby])
    end
    K --- UC1
    K --- UC2
    A --- UC3
    K --- UC4
```

## 4.3. Specyfikacje przypadków użycia

### UC-01: Zarezerwuj zasób

| Pole | Opis |
|---|---|
| Aktor główny | Klient |
| Cel | |
| Powiązania | WF-01, US-01 |
| Warunki początkowe | Klient jest zalogowany. |
| Warunki końcowe (sukces) | Rezerwacja zapisana ze statusem POTWIERDZONA. |
| Wyzwalacz | |

**Scenariusz główny:**

1. Klient wybiera opcję „Nowa rezerwacja”.
2. System wyświetla listę zasobów.
3. …

**Scenariusze alternatywne / wyjątki:**

- 4a. Termin zajęty: System wyświetla komunikat i proponuje najbliższy wolny termin. Powrót do kroku 3.

## 4.4. Diagramy sekwencji kluczowych interakcji

```mermaid
sequenceDiagram
    actor K as Klient
    participant UI as Aplikacja web
    participant API as Backend API
    participant DB as Baza danych
    K->>UI: wybiera termin i potwierdza
    UI->>API: POST /api/reservations
    API->>DB: sprawdź kolizje
    DB-->>API: brak kolizji
    API->>DB: INSERT reservation
    API-->>UI: 201 Created
    UI-->>K: potwierdzenie
```

## 4.5. Diagramy stanów (dla obiektów z cyklem życia)

```mermaid
stateDiagram-v2
    [*] --> NOWA
    NOWA --> POTWIERDZONA: potwierdzenie
    NOWA --> ANULOWANA: anulowanie
    POTWIERDZONA --> ANULOWANA: anulowanie (≥ 24 h przed)
    POTWIERDZONA --> ZREALIZOWANA: upływ terminu
    ANULOWANA --> [*]
    ZREALIZOWANA --> [*]
```
