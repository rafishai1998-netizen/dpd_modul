# Funkcje brakujące i zbędne — etap modelowania

## Cel dokumentu

Ten dokument porządkuje pierwszy etap projektu: ustalenie, czego brakuje w makiecie, co jest konieczne w jednym module nadań DPD, a co jest zbędne na start.

## Funkcje brakujące w makiecie lub wymagające doprecyzowania

1. Kolejka zamówień do nadania.
2. Formularz nadania paczki po wybraniu zamówienia.
3. Obsługa multi-paczek.
4. Automatyczne rozpoznanie COD i kwoty pobrania.
5. Szablony paczek: 1 kg, 5 kg, kreda 20 kg, worek 30 kg, wiadro, wielopaczka kreda.
6. Reguły produktów: 20 kg, 30 kg, waga 0 kg, produkty ciężkie, płynne i żywe.
7. Walidacja telefonu, kodu pocztowego, miasta, ulicy, wagi i COD.
8. Blokada ponownego nadania zamówienia z numerem listu.
9. Jasny workflow: Nadaj, Nadaj i drukuj, Drukuj etykietę, Kopiuj tracking, Otwórz zamówienie.
10. Historia operacji z datą, pracownikiem, ID zamówienia, FID, numerem listu, wynikiem i błędem.
11. Diagnostyka modułu, tabel, etykiet, uprawnień i ostatnich błędów.
12. Dashboard pokazujący liczbę zamówień do nadania, do wydruku, z błędami, COD i nadanych dzisiaj.

## Funkcje obowiązkowe w pierwszym modelu

- jeden moduł Back Office,
- jedna główna kolejka pracy,
- jedna historia operacji,
- jeden panel ustawień,
- jeden panel diagnostyki,
- praca na istniejącej integracji API DPD po dodaniu podstawy modułu.

## Funkcje zbędne na pierwszy etap

- osobne moduły `dpdshipmvp`, `dpdpackoffice`, `orderpanelmvp`,
- integracja z innymi kurierami,
- automatyczne nadawanie bez kliknięcia operatora,
- przebudowa API DPD,
- zmiany w checkout,
- zmiany w core PrestaShop,
- pełny system magazynowy,
- aplikacja mobilna,
- terminal drukarki lokalnej,
- analiza kosztów i dopłat,
- porównanie z fakturami DPD,
- pełna synchronizacja statusów w tle.

## Następny krok

1. Replit poprawia makietę zgodnie z brakującymi funkcjami.
2. GitHub przechowuje dokumentację i Issues.
3. Codex najpierw analizuje repozytorium i dokumentację.
4. Kodowanie zaczyna się dopiero po zatwierdzeniu modelu i po dodaniu podstawy modułu z gotowym API DPD.
