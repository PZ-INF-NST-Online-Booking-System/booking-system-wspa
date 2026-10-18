# Zasady pracy z repozytorium

## Przepływ pracy (GitHub Flow / GitLab Flow)

1. **Zadanie**: każda praca zaczyna się od Issue z osobą przypisaną, etykietą (`m1`…`m4`) i krótkim opisem „co ma powstać”.
2. **Gałąź**: tworzysz gałąź od aktualnego `main`:
   ```bash
   git switch main
   git pull
   git switch -c 12-slownik-pojec      # <nr issue>-<krótki-opis>
   ```
3. **Commity**: commituj małymi krokami, w trybie rozkazującym, po polsku:
   ```
   docs: dodaj pojęcia dotyczące rezerwacji do słownika (#12)
   ```
   Typy: `docs:` (treść), `diag:` (diagramy), `fix:` (poprawki), `chore:` (porządki w repo).
4. **Pull/Merge Request**: wypychasz gałąź (`git push -u origin 12-slownik-pojec`) i otwierasz PR/MR. W opisie wpisz `Closes #12`.
5. **Recenzja**: co najmniej **jedna inna osoba** zatwierdza PR/MR. Recenzent sprawdza poprawność merytoryczną i spójność z resztą dokumentacji, m.in. pojęcia ze słownika i identyfikatory.
6. **Scalenie**: autor scala PR/MR po zatwierdzeniu, a gałąź usuwa.

## Zasady

- Nie wysyłamy commitów bezpośrednio do `main`, bo gałąź jest chroniona (*branch protection* / *protected branch*).
- Jeden PR/MR dotyczy jednej rzeczy. Lepiej kilka małych niż jeden ogromny.
- Diagramy zapisujemy jako kod **Mermaid** w plikach `.md`. Obrazy (makiety) trzymamy w `docs/makiety/` jako PNG/SVG, a w dokumencie dajemy link do źródła (Figma/Penpot).
- Nie dodajemy plików binarnych `.docx`/`.pdf` jako źródła dokumentacji. Źródłem jest Markdown.
- Konflikty rozwiązuje autor PR/MR, a w razie wątpliwości konsultuje się z właścicielem sekcji.

## Oddanie kamienia milowego

Robi to kierownik projektu po scaleniu wszystkich PR/MR danego etapu:

```bash
git switch main && git pull
git tag -a m2 -m "Kamień milowy M2: wymagania"
git push origin m2
```

Następnie tworzy *Release* (GitHub) albo *Release* w GitLab z tego tagu i krótko opisuje, co się zmieniło.
