# PROJECT BRIEF — jeden moduł nadań DPD

## Cel

Zbudować jeden moduł PrestaShop do obsługi nadań DPD w Back Office. Moduł ma łączyć kolejkę zamówień do nadania, formularz nadania, multi-paczki, COD, druk etykiet, historię, błędy danych, szablony paczek, reguły produktów i diagnostykę.

## Decyzja nadrzędna

Nie budujemy trzech osobnych modułów.

Nazwy `dpdshipmvp`, `dpdpackoffice` i `orderpanelmvp` można traktować wyłącznie jako obszary logiczne jednego modułu:

- obszar nadania paczki,
- obszar wydruku i etykiet,
- obszar kolejki zamówień i pakowania.

W kodzie oraz dokumentacji docelowo należy myśleć o jednym module nadań DPD.

## Zasada krytyczna API DPD

Podstawa modułu zostanie dodana później. W tej podstawie istnieje gotowe połączenie z API DPD.

Nie przebudowujemy tej integracji. Nie tworzymy drugiego klienta API. Nowe funkcje mają korzystać z istniejącego silnika API DPD, gdy zostanie dodany do repozytorium.

## Zakres v1

- osobna zakładka Back Office,
- Dashboard,
- Do nadania,
- Do wydruku,
- Nadane dzisiaj,
- Błędy danych,
- Historia,
- Szablony paczek,
- Reguły produktów,
- Ustawienia,
- Diagnostyka,
- tabela zamówień i przesyłek,
- formularz nadania paczki,
- obsługa COD,
- obsługa wielu paczek do jednego zamówienia,
- FID i numer listu,
- status etykiety,
- wydruk pojedynczy,
- wydruk zbiorczy A6 i A4,
- wariant z listą produktów,
- historia operacji,
- ostrzeżenia przed ponownym drukiem,
- blokada ponownego nadania,
- walidacja danych.

## Poza zakresem v1

- osobne moduły `dpdshipmvp`, `dpdpackoffice`, `orderpanelmvp`,
- integracja z innymi kurierami,
- automatyczne nadawanie bez kliknięcia operatora,
- przebudowa API DPD,
- zmiana checkout,
- modyfikacja core PrestaShop,
- pełny system magazynowy,
- aplikacja mobilna,
- terminal drukarki lokalnej,
- analiza kosztów i dopłat,
- porównanie z fakturami DPD,
- pełna synchronizacja statusów w tle.

## Aktualny etap

Aktualny etap to modelowanie przedsięwzięcia, funkcji, workflow i makiety. Jeszcze nie kodujemy finalnego API. Najpierw ustalamy, jak moduł ma działać, co jest potrzebne, czego brakuje w makiecie i co jest zbędne.

## Wymagania techniczne

- PrestaShop 9.x,
- PHP zgodny ze środowiskiem sklepu,
- kontrolery Back Office,
- tokeny, uprawnienia i CSRF,
- walidacja danych wejściowych,
- brak modyfikacji core,
- minimalny zakres zmian,
- brak sekretów w logach.

## Źródło UX

Makieta:
`02_mockup/dpdpackoffice-makieta-v4.html`

Pełne wytyczne:
`README.md` oraz `docs/PROJECT_SUMMARY_4800.md`.
