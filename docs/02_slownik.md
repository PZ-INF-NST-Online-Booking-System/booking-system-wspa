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
| Administrator | Administrator | Osoba, która prowadzi system w imieniu Usługodawcy: zarządza Usługami, Pracownikami, Grafikami dostępności, Kartoteką klientów i Rezerwacjami oraz ustawia reguły rezerwowania. Zwykle jest to właściciel firmy albo osoba na recepcji. | admin, kierownik, menedżer | Właścicielka salonu codziennie rano sprawdza kalendarz Rezerwacji na cały dzień. | Usługodawca, Pracownik, Kartoteka klientów |
| Anulowanie rezerwacji | Cancellation | Odwołanie Rezerwacji przed jej Terminem. Rezerwację może anulować Klient (przez Link do anulowania, w granicach Reguły anulowania) albo Administrator. Po anulowaniu Termin znów staje się Wolnym terminem. | odwołanie, rezygnacja, skasowanie wizyty | Klient anuluje strzyżenie zaplanowane na piątek, bo zachorował. | Rezerwacja, Reguła anulowania, Link do anulowania, Status rezerwacji |
| Czas buforowy | BufferTime | Przerwa doliczana automatycznie po każdej Rezerwacji, przeznaczona na sprzątanie stanowiska i przygotowanie do kolejnego Klienta. W tym czasie nie można zarezerwować następnej Usługi u tego samego Pracownika. | przerwa techniczna, przerwa między wizytami | 15 minut po strzyżeniu | Usługa, Wolny termin |
| Dzień wolny | DayOff | Dzień, w którym Pracownik nie przyjmuje Klientów, mimo że zwykle w tym dniu pracuje (np. urlop, choroba, święto). W Dniu wolnym system nie pokazuje Wolnych terminów u tego Pracownika. | urlop, nieobecność pracownika | Pracownik ma Dzień wolny 24 grudnia. | Grafik dostępności, Pracownik, Wyjątek w grafiku |
| Grafik dostępności | Schedule | Stałe godziny pracy Pracownika w poszczególnych dniach tygodnia, w których może przyjmować Klientów. Na jego podstawie system wyznacza Wolne terminy. | grafik pracy, harmonogram, kalendarz pracownika | Pracownik pracuje od poniedziałku do piątku w godzinach 9:00-17:00. | Pracownik, Dzień wolny, Wyjątek w grafiku, Wolny termin |
| Horyzont rezerwacji | BookingHorizon | Liczba dni do przodu, na ile Klient może zarezerwować Termin. Terminów późniejszych niż horyzont system nie pokazuje. Ustala go Administrator. | okres rezerwacji, wyprzedzenie | Horyzont 60 dni: 1 marca można zarezerwować Termin najpóźniej na 30 kwietnia. | Rezerwacja, Wolny termin |
| Kartoteka klientów | ClientDirectory | Zbiór danych kontaktowych wszystkich Klientów, którzy zarezerwowali Usługę, wraz z listą ich Rezerwacji. Prowadzi ją Usługodawca. | baza klientów, lista klientów | Administrator wyszukuje w Kartotece klientów panią Nowak i widzi jej trzy ostatnie Rezerwacje. | Klient, Rezerwacja, Administrator |
| Klient | Client | Osoba, która rezerwuje Usługę u Usługodawcy. Nie zakłada konta: podaje swoje dane przy każdej Rezerwacji i dostaje Powiadomienia e-mailem. | pacjent, gość, użytkownik | Pani Anna rezerwuje manicure na sobotę o 10:00. | Rezerwacja, Kartoteka klientów, Powiadomienie |
| Krok terminu | SlotInterval | Odstęp czasu między kolejnymi godzinami rozpoczęcia, które system proponuje Klientowi przy wyborze Terminu. Ustala go Administrator. | interwał, siatka godzin | Krok 15 minut: system proponuje godziny 9:00, 9:15, 9:30 itd. | Termin, Wolny termin |
| Link do anulowania | CancellationLink | Jednorazowy odnośnik w wiadomości e-mail, przez który Klient może sam anulować swoją Rezerwację, bez logowania i bez telefonu do Usługodawcy. | link rezygnacji | Klient klika „Anuluj rezerwację” w e-mailu z potwierdzeniem. | Anulowanie rezerwacji, Powiadomienie, Reguła anulowania |
| Powiadomienie | Notification | Wiadomość e-mail, którą system wysyła Klientowi w sprawie jego Rezerwacji: potwierdzenie Rezerwacji, Przypomnienie albo informację o Anulowaniu rezerwacji. Jeśli wysyłka się nie uda, system zapisuje to i próbuje wysłać wiadomość ponownie. | wiadomość, mail, notyfikacja | E-mail „Potwierdzamy Twoją rezerwację: strzyżenie, 12.11, 14:00”. | Klient, Rezerwacja, Przypomnienie, Link do anulowania |
| Pracownik | Employee | Osoba zatrudniona u Usługodawcy, która wykonuje Usługi. Ma własny Grafik dostępności, loguje się do systemu i widzi swoje Rezerwacje. | specjalista, fryzjer, kosmetyczka, stylista | Fryzjerka Kasia wykonuje strzyżenie i koloryzację. | Usługa, Grafik dostępności, Rezerwacja |
| Przypomnienie | Reminder | Powiadomienie wysyłane Klientowi przed Terminem Rezerwacji, żeby o niej nie zapomniał. | monit | E-mail wysłany 24 godziny przed Terminem. | Powiadomienie, Rezerwacja |
| Reguła anulowania | CancellationPolicy | Ustalony przez Usługodawcę czas przed Terminem, do którego Klient może sam anulować Rezerwację. Po tym czasie Rezerwację może anulować tylko Administrator. | polityka anulowania, zasady odwołań | Klient może anulować Rezerwację najpóźniej 24 godziny przed Terminem. | Anulowanie rezerwacji, Link do anulowania |
| Rezerwacja | Booking | Umówienie Klienta na konkretną Usługę u konkretnego Pracownika w określonym Terminie. Rezerwacja ma Status rezerwacji. | wizyta, zapis, wizyta umówiona, booking | Rezerwacja: Anna Nowak, manicure, Kasia, 15.11, 10:00-11:00. | Klient, Usługa, Pracownik, Termin, Status rezerwacji |
| Status rezerwacji | BookingStatus | Etap, na którym jest Rezerwacja. Możliwe wartości opisuje sekcja „Status rezerwacji” poniżej. | stan rezerwacji | POTWIERDZONA | Rezerwacja, Anulowanie rezerwacji |
| Termin | TimeSlot | Data i godzina rozpoczęcia Usługi. Czas zakończenia wynika z czasu trwania Usługi. | slot, godzina wizyty, data wizyty | 15.11, godz. 10:00 | Rezerwacja, Wolny termin, Krok terminu |
| Usługa | Service | Zabieg lub czynność, którą Usługodawca oferuje Klientom. Ma nazwę, opis, czas trwania i cenę oraz listę Pracowników, którzy ją wykonują. | zabieg, oferta, pozycja cennika | Strzyżenie damskie, 45 minut, 80 zł | Pracownik, Rezerwacja, Czas buforowy |
| Usługodawca | ServiceProvider | Firma, która przyjmuje Klientów na Usługi według Terminów: gabinet, salon lub konsultant, zatrudniający od jednej do kilku osób. W jednym systemie jest jeden Usługodawca. | salon, gabinet, firma, placówka | Salon fryzjerski z trzema Pracownikami | Administrator, Pracownik, Usługa |
| Wolny termin | AvailableSlot | Termin, który Klient może zarezerwować: mieści się w Grafiku dostępności Pracownika, nie jest Dniem wolnym, nie koliduje z inną Rezerwacją (łącznie z Czasem buforowym) i nie wykracza poza Horyzont rezerwacji. | dostępna godzina, okienko | U Kasi 15.11 wolne są godziny 9:00 i 11:15. | Termin, Grafik dostępności, Czas buforowy, Horyzont rezerwacji |
| Wyjątek w grafiku | ScheduleException | Jednorazowa zmiana godzin pracy Pracownika w wybranym dniu, inna niż w jego Grafiku dostępności. | zmiana grafiku, zastępstwo | 20.11 Kasia pracuje wyjątkowo od 12:00 do 20:00. | Grafik dostępności, Dzień wolny |

## Wartości wyliczeniowe

### Status rezerwacji

| Wartość | Znaczenie | Kiedy Rezerwacja go dostaje |
|---|---|---|
| POTWIERDZONA | Rezerwacja jest ważna, a Termin jest zajęty dla innych Klientów. | Od razu po złożeniu Rezerwacji przez Klienta na publicznej stronie rezerwacji. Usługodawca nie musi jej akceptować. |
| ZREALIZOWANA | Termin Rezerwacji minął, a Rezerwacja nie została anulowana. Status nie oznacza, że Klient na pewno przyszedł. | Automatycznie po upływie Terminu (po zakończeniu Usługi). |
| ANULOWANA | Rezerwacja została odwołana, a Termin znów jest Wolnym terminem. | W chwili Anulowania rezerwacji przez Klienta (Linkiem do anulowania, w granicach Reguły anulowania) albo przez Administratora. |

Statusy ZREALIZOWANA i ANULOWANA są końcowe: Rezerwacja nie może już zmienić statusu.

### Rola konta

| Wartość | Znaczenie |
|---|---|
| ADMINISTRATOR | Konto Administratora, z dostępem do wszystkich funkcji panelu administracyjnego. |
| PRACOWNIK | Konto Pracownika, z dostępem do własnego Grafiku dostępności i własnych Rezerwacji. |

Klient nie ma konta, więc nie ma też roli.
