# PROJECT BRIEF — DPD Pack Office

## Cel

Zbudować moduł PrestaShop 9 zapewniający osobny panel Back Office do obsługi już utworzonych przesyłek DPD, etykiet, wydruków, statusów, błędów i historii operacji.

## Główne role modułów

### `dpdshipmvp`
Odpowiada za:

- utworzenie przesyłki,
- komunikację z API DPD,
- zapis FID,
- pobranie numeru listu,
- pobranie etykiety,
- operacje ręczne na stronie zamówienia.

### `dpdpackoffice`
Odpowiada za:

- listę już utworzonych przesyłek,
- wydruki pojedyncze i zbiorcze,
- kontrolę statusów,
- historię,
- diagnostykę,
- ostrzeżenia przed powtórnym drukiem i nadaniem.

### `orderpanelmvp`
Odpowiada za:

- listę zamówień do kompletacji i pakowania,
- nie komunikuje się bezpośrednio z API DPD.

## Zakres v1

- osobna zakładka Back Office,
- tabela przesyłek,
- wyszukiwanie i filtrowanie,
- status przesyłki,
- numer listu,
- FID,
- liczba paczek,
- waga każdej paczki,
- ręczne korekty wagi,
- minimalna waga 1 kg,
- COD TAK/NIE,
- status etykiety,
- wydruk pojedynczy,
- wydruk zbiorczy A6 i A4,
- wariant z listą produktów,
- historia operacji,
- diagnostyka,
- ostrzeżenia przed ponownym drukiem,
- blokada niebezpiecznych operacji.

## Poza zakresem v1

- modyfikacja core PrestaShop,
- override core,
- zmiana checkout,
- tworzenie przewoźnika,
- automatyczne wywołanie API przy otwarciu panelu,
- automatyczne nadanie bez jawnej akcji operatora,
- przechowywanie tokenów i haseł w logach,
- pełny terminal drukarki lokalnej bez osobnego projektu.

## Wymagania techniczne

- PrestaShop 9.x,
- PHP zgodny ze środowiskiem sklepu,
- Symfony services tam, gdzie uzasadnione,
- osobne tabele modułu,
- kontrolery Back Office,
- tokeny, uprawnienia i CSRF,
- walidacja wszystkich danych wejściowych,
- brak modyfikacji core,
- minimalny zakres zmian.

## Źródło UX

Makieta:
`02_mockup/dpdpackoffice-makieta-v4.html`
