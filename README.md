# Moduł nadań DPD — instrukcja projektu

## 1. Cel projektu

Projekt dotyczy budowy jednego modułu nadań DPD dla PrestaShop.

Moduł ma usprawnić codzienną obsługę wysyłek w firmie RaFish: nadawanie paczek, obsługę pobrań COD, wielopaczki, druk etykiet, kontrolę błędów adresowych, historię operacji oraz diagnostykę.

Repozytorium główne projektu:

```text
https://github.com/rafishai1998-netizen/dpd_modul
```

GitHub jest centrum projektu. Wszystkie ustalenia, dokumentacja, makiety, Issues, raporty i kod mają odnosić się do tego repozytorium.

## 2. Najważniejsza decyzja projektowa

Tworzymy jeden moduł nadań DPD.

Nie budujemy trzech osobnych modułów. Nazwy takie jak `dpdshipmvp`, `dpdpackoffice` i `orderpanelmvp` mogą być traktowane wyłącznie jako obszary logiczne lub sekcje jednego modułu.

Docelowy moduł może mieć sekcje:

- Dashboard,
- Do nadania,
- Do wydruku,
- Nadane dzisiaj,
- Błędy danych,
- Historia,
- Szablony paczek,
- Reguły produktów,
- Ustawienia,
- Diagnostyka.

## 3. Krytyczna zasada techniczna

Moduł ma już swoją podstawę, ale zostanie dodana do repozytorium później, gdy będzie dostępna.

W tej podstawie jest już opanowane połączenie z API DPD.

Nie wolno zmieniać mechanizmu połączenia z API DPD pod żadnym pozorem.

To oznacza:

- nie przebudowywać klienta API DPD,
- nie zmieniać sposobu autoryzacji,
- nie zmieniać obsługi FID,
- nie zmieniać istniejących metod tworzenia przesyłek,
- nie przepisywać integracji DPD od zera,
- nie dodawać drugiego niezależnego połączenia z DPD,
- nie zapisywać nowych danych API, loginów, haseł ani tokenów w innym miejscu.

Nowy kod ma korzystać z istniejącej integracji jako z gotowego silnika.

## 4. Aktualny etap

Aktualny etap to modelowanie przedsięwzięcia, a nie finalne kodowanie.

Na tym etapie trzeba ustalić:

- jak ma wyglądać panel,
- jakie funkcje są potrzebne,
- jak wygląda proces nadania paczki,
- które funkcje są zbędne,
- czego brakuje w obecnej makiecie,
- jakie zadania trzeba przygotować dla Codexa,
- co Replit ma poprawić w makiecie,
- jak GitHub ma porządkować dokumentację i Issues.

Nie wolno na tym etapie ruszać API DPD.

## 5. Role narzędzi

### ChatGPT

ChatGPT jest koordynatorem projektu.

Zadania:

- analiza wymagań,
- porządkowanie funkcji,
- przygotowanie instrukcji dla Codexa i Replit,
- tworzenie dokumentacji,
- rozbijanie prac na Issues,
- kontrola ryzyk,
- pilnowanie zasady: jedno repo, jeden moduł, API DPD nietykalne.

### GitHub

GitHub jest źródłem prawdy.

W repozytorium mają być:

- README,
- dokumentacja projektu,
- makiety,
- Issues,
- decyzje projektowe,
- raporty,
- test plan,
- kod modułu,
- historia zmian.

Zasady:

- nie pracować bezpośrednio na `main`,
- każda funkcja ma mieć osobny branch,
- każda większa zmiana ma mieć Issue,
- każda implementacja ma mieć opis testów,
- nie wrzucać haseł, tokenów ani danych API.

### Codex

Codex jest wykonawcą technicznym.

Codex musi najpierw:

1. przeanalizować repozytorium,
2. sprawdzić dokumentację,
3. znaleźć istniejące elementy modułu,
4. poczekać na podstawę modułu z gotową integracją API DPD,
5. określić, czego brakuje,
6. dopiero potem implementować.

Codexowi nie wolno:

- zmieniać połączenia z API DPD,
- tworzyć nowej integracji DPD,
- modyfikować core PrestaShop,
- robić override bez wyraźnej decyzji,
- tworzyć przesyłek automatycznie po wejściu do panelu,
- zapisywać sekretów w kodzie,
- robić dużych zmian bez raportu.

Po każdej pracy Codex ma podać:

- co zmienił,
- jakie pliki zmienił,
- jak to przetestować,
- czy dotknął bazy danych,
- czy dotknął API DPD,
- czy dotknął zamówień PrestaShop,
- jakie są ryzyka,
- czego nie przetestował.

### Replit

Replit służy do makiet i prototypów wyglądu.

Replit nie jest głównym miejscem budowy modułu.

Replit ma służyć do:

- podglądu HTML,
- poprawiania układu panelu,
- testowania workflow,
- sprawdzania wyglądu tabel, filtrów i formularzy,
- projektowania interfejsu operatora.

Replit nie powinien:

- łączyć się z prawdziwym API DPD,
- przechowywać danych API,
- tworzyć realnych przesyłek,
- zastępować repozytorium GitHub,
- być traktowany jako finalny kod produkcyjny.

## 6. Funkcje obowiązkowe modułu

### Kolejka zamówień do nadania

Panel powinien pokazywać zamówienia gotowe do wysyłki.

Na liście powinny być widoczne:

- ID zamówienia,
- referencja,
- klient,
- telefon,
- e-mail,
- adres,
- status zamówienia,
- forma płatności,
- kwota,
- COD TAK/NIE,
- metoda dostawy,
- produkty,
- liczba produktów,
- ostrzeżenia,
- informacja, czy zamówienie ma już list DPD.

### Formularz nadania paczki

Po wybraniu zamówienia operator powinien widzieć formularz:

- dane odbiorcy,
- telefon,
- e-mail,
- adres,
- liczba paczek,
- waga paczki,
- wymiary,
- usługa DPD,
- kwota COD,
- uwagi dla kuriera,
- szablon paczki,
- przyciski akcji.

Przyciski:

- Nadaj,
- Nadaj i drukuj,
- Drukuj etykietę,
- Kopiuj tracking,
- Otwórz zamówienie.

### Multi-paczki

Moduł musi obsługiwać kilka paczek do jednego zamówienia.

Każda paczka powinna mieć:

- numer paczki,
- wagę,
- długość,
- szerokość,
- wysokość,
- ewentualną uwagę.

Moduł powinien sumować wagę i ostrzegać, gdy paczka jest zbyt ciężka.

### COD

Moduł powinien automatycznie rozpoznawać pobranie.

Dla COD powinien pokazywać:

- kwotę pobrania,
- metodę płatności,
- ostrzeżenie przy braku kwoty,
- ostrzeżenie przy ręcznej zmianie kwoty.

Kwota COD domyślnie powinna pochodzić z zamówienia.

### Szablony paczek

Potrzebne są szybkie szablony:

- Mała paczka 1 kg,
- Standard 5 kg,
- Kreda 20 kg,
- Worek 30 kg,
- Wiadro,
- Wielopaczka kreda.

### Reguły produktów

Przykładowe reguły:

- nazwa zawiera „20 kg” → zasugeruj paczkę 20–22 kg,
- nazwa zawiera „30 kg” → pokaż ostrzeżenie o limicie,
- produkt ma wagę 0 kg → pokaż błąd,
- kategoria kreda → pokaż ostrzeżenie „produkt ciężki”,
- produkt płynny → pokaż ostrzeżenie „zabezpieczyć przed wyciekiem”,
- produkt żywy / ryby → pokaż ostrzeżenie specjalne.

### Walidacja danych

Przed nadaniem moduł powinien sprawdzić:

- brak telefonu,
- błędny telefon,
- brak kodu pocztowego,
- zły format kodu,
- brak miasta,
- brak ulicy,
- waga 0 kg,
- waga poniżej 1 kg,
- COD bez kwoty,
- zamówienie już nadane.

Błędy krytyczne powinny blokować nadanie.

### Blokada ponownego nadania

Jeżeli zamówienie ma już numer listu, moduł nie może po prostu utworzyć kolejnej przesyłki.

Musi pokazać ostrzeżenie:

```text
To zamówienie ma już list DPD.
Ponowne nadanie może utworzyć drugi list i dodatkowy koszt.
```

Dostępne opcje:

- Drukuj istniejącą etykietę,
- Dodaj kolejną paczkę,
- Ponów nadanie po potwierdzeniu,
- Anuluj.

### Druk etykiet

Moduł powinien obsługiwać:

- druk pojedynczy,
- ponowny druk,
- druk zbiorczy,
- format A6,
- format A4,
- etykieta + lista produktów.

Ponowny druk musi wymagać potwierdzenia.

### Historia operacji

Każda operacja powinna być zapisana.

Historia powinna zawierać:

- datę i czas,
- ID pracownika,
- ID zamówienia,
- typ operacji,
- FID,
- numer listu,
- wynik,
- komunikat błędu,
- identyfikator korelacyjny.

### Diagnostyka

Panel diagnostyczny powinien pokazywać:

- czy moduł działa,
- czy istnieje podstawa modułu,
- czy dostępna jest usługa API DPD,
- czy są wymagane tabele,
- ostatnie błędy,
- problemy z etykietami,
- problemy z uprawnieniami.

Nie wolno pokazywać sekretów, tokenów ani haseł.

## 7. Funkcje zbędne na pierwszy etap

Na start nie robimy:

- osobnych modułów `dpdshipmvp`, `dpdpackoffice`, `orderpanelmvp`,
- integracji z innymi kurierami,
- automatycznego nadawania paczek bez kliknięcia operatora,
- przebudowy API DPD,
- zmian w checkout,
- zmian w core PrestaShop,
- pełnego systemu magazynowego,
- aplikacji mobilnej,
- terminala drukarki lokalnej,
- analizy kosztów i dopłat,
- automatycznego porównywania z fakturami DPD,
- pełnej synchronizacji statusów DPD w tle.

Te funkcje mogą wrócić później, ale nie w pierwszym etapie.

## 8. Pierwszy etap pracy

Pierwszy etap ma odpowiedzieć:

```text
Jak dokładnie ma działać cały moduł?
```

Do wykonania:

1. przeanalizować obecną makietę,
2. wypisać funkcje obecne w makiecie,
3. wypisać funkcje brakujące,
4. wypisać funkcje zbędne,
5. poprawić makietę w Replit,
6. zaktualizować dokumentację w GitHub,
7. stworzyć Issues dla Codexa,
8. dopiero potem czekać na podstawę modułu z gotowym API DPD.

## 9. Komenda startowa dla tego projektu

W rozmowach projektowych wystarczy komenda:

```text
Działaj w trybie projektu DPD.
```

Oznacza ona:

- GitHub jest centrum,
- projekt dotyczy jednego modułu nadań DPD,
- API DPD jest nietykalne,
- podstawa modułu zostanie dodana później,
- teraz projektujemy model funkcji i makietę,
- Codex dostaje małe zadania,
- Replit poprawia tylko makietę,
- każda decyzja powinna trafić do dokumentacji lub Issues.

## 10. Najbliższy kierunek

Najbliższe zadania:

1. zaktualizować dokumentację: „jeden moduł, API DPD nietykalne”,
2. poprawić obecne Issues, bo część mówi jeszcze o osobnych modułach,
3. przygotować listę funkcji brakujących w makiecie,
4. przygotować listę funkcji zbędnych,
5. zlecić Replitowi poprawę makiety,
6. dopiero po zatwierdzeniu makiety dać Codexowi etap analizy.
