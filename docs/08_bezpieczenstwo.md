# 08. Bezpieczeństwo i ochrona danych

## 8.1. Role i uprawnienia

| Uprawnienie / operacja | Klient | Administrator |
|---|---|---|
| Przeglądanie zasobów | ✔ | ✔ |
| Tworzenie i anulowanie rezerwacji | ✔ (własne) | ✔ (wszystkie) |
| Zarządzanie zasobami | | ✔ |

## 8.2. Uwierzytelnianie i sesje

<!-- Sposób logowania, polityka haseł (np. wg NIST SP 800-63B), MFA, czas życia sesji/tokenu, reset hasła. -->

## 8.3. Analiza zagrożeń (STRIDE)

| Zagrożenie | Przykład w naszym systemie | Zabezpieczenie | WNF |
|---|---|---|---|
| **S**poofing (podszywanie się) | | | |
| **T**ampering (manipulacja danymi) | | | |
| **R**epudiation (wypieranie się) | | dziennik audytowy | |
| **I**nformation disclosure (ujawnienie) | | | |
| **D**enial of service | | | |
| **E**levation of privilege | | | |

## 8.4. OWASP Top 10 — zastosowane środki

| Kategoria OWASP | Środek w projekcie |
|---|---|
| A01 Broken Access Control | kontrola uprawnień po stronie serwera dla każdego endpointu |
| A03 Injection | zapytania parametryzowane / ORM |
| … | |

## 8.5. Ochrona danych osobowych (RODO)

- Zakres przetwarzanych danych osobowych i podstawa prawna: …
- Minimalizacja danych: …
- Prawa osoby (dostęp, sprostowanie, usunięcie, eksport): jak system je realizuje …
- Szyfrowanie: w tranzycie (TLS), w spoczynku (…), hasła (bcrypt/Argon2) …
- Kopie zapasowe i retencja: …

## 8.6. Dziennik audytowy

<!-- Jakie zdarzenia są logowane, jakie dane (bez danych wrażliwych w logach!), jak długo przechowywane. -->
