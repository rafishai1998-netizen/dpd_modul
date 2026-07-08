# Streszczenie instrukcji projektu DPD

Projekt dotyczy budowy jednego modułu nadań DPD dla PrestaShop. Nie budujemy trzech osobnych modułów. Wszystkie funkcje mają działać w ramach jednego modułu, podzielonego najwyżej na sekcje: Dashboard, Do nadania, Do wydruku, Nadane dzisiaj, Błędy danych, Historia, Szablony paczek, Reguły produktów, Ustawienia i Diagnostyka.

Repozytorium główne:
https://github.com/rafishai1998-netizen/dpd_modul

GitHub jest centrum projektu. Wszystkie ustalenia, dokumentacja, makiety, Issues, raporty i kod mają odnosić się do tego repozytorium.

Najważniejsza zasada techniczna: moduł ma już swoją podstawę, ale zostanie dodana później. W tej podstawie jest już opanowane połączenie z API DPD. Nie wolno zmieniać mechanizmu połączenia z API DPD pod żadnym pozorem. Nie przebudowywać klienta API, nie zmieniać autoryzacji, FID, metod tworzenia przesyłek, nie pisać integracji od zera i nie dodawać drugiego połączenia z DPD. Nowy kod ma korzystać z istniejącej integracji jako gotowego silnika.

Aktualny etap to modelowanie przedsięwzięcia, funkcji, workflow i makiety. Jeszcze nie kodujemy finalnego API. Najpierw ustalamy, jak moduł ma działać, jakie funkcje są potrzebne, czego brakuje w makiecie, które funkcje są zbędne i jakie zadania przygotować dla Codexa oraz Replit.

Role narzędzi:
ChatGPT koordynuje projekt, analizuje wymagania, przygotowuje instrukcje, aktualizuje dokumentację i pilnuje zasady: jeden moduł, API DPD nietykalne.
GitHub jest źródłem prawdy: dokumentacja, Issues, makiety, raporty, kod i historia zmian.
Codex jest wykonawcą technicznym. Ma robić małe zadania po analizie repozytorium. Nie wolno mu ruszać API DPD ani core PrestaShop.
Replit służy tylko do makiet HTML/CSS/JS i testowania workflow. Nie łączy się z prawdziwym API DPD.

Funkcje obowiązkowe modułu:
1. Kolejka zamówień do nadania z ID, klientem, adresem, telefonem, e-mailem, statusem, płatnością, kwotą, COD, metodą dostawy, produktami i ostrzeżeniami.
2. Formularz nadania paczki z danymi odbiorcy, wagą, wymiarami, liczbą paczek, usługą DPD, COD, uwagami, szablonem i przyciskami: Nadaj, Nadaj i drukuj, Drukuj etykietę, Kopiuj tracking, Otwórz zamówienie.
3. Multi-paczki, czyli kilka paczek do jednego zamówienia, z wagą i wymiarami każdej paczki.
4. Obsługa COD z automatycznym rozpoznaniem pobrania i kwotą z zamówienia.
5. Szablony paczek: 1 kg, 5 kg, kreda 20 kg, worek 30 kg, wiadro, wielopaczka kreda.
6. Reguły produktów: wykrywanie 20 kg, 30 kg, wagi 0 kg, produktów ciężkich, płynnych i żywych.
7. Walidacja telefonu, kodu pocztowego, miasta, ulicy, wagi, COD i stanu nadania.
8. Blokada ponownego nadania zamówienia, które ma już numer listu.
9. Druk etykiet: pojedynczy, ponowny, zbiorczy, A6, A4, etykieta + lista produktów.
10. Historia operacji z datą, pracownikiem, ID zamówienia, FID, numerem listu, wynikiem, błędem i identyfikatorem korelacyjnym.
11. Diagnostyka modułu, tabel, API, etykiet, uprawnień i ostatnich błędów. Bez pokazywania sekretów.

Funkcje zbędne na pierwszy etap: osobne moduły dpdshipmvp/dpdpackoffice/orderpanelmvp, inni kurierzy, automatyczne nadawanie bez kliknięcia, przebudowa API DPD, zmiany w checkout, zmiany w core PrestaShop, pełny system magazynowy, aplikacja mobilna, terminal drukarki lokalnej, analiza kosztów i dopłat, porównanie z fakturami DPD, pełna synchronizacja statusów w tle.

Komenda startowa:
„Działaj w trybie projektu DPD.”

Pełne wytyczne są w pliku README przygotowanym dla projektu. To streszczenie ma ograniczenie długości, więc wszystkie szczegółowe zasady, funkcje, role narzędzi i ograniczenia techniczne należy traktować jako opisane szerzej w pliku README.
