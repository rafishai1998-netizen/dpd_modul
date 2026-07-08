# PLAN TESTÓW

## 1. Testy statyczne

- składnia PHP,
- zgodność nazw klas i plików,
- poprawność namespace,
- brak odwołań do nieistniejących metod,
- poprawność SQL,
- poprawność instalatora,
- brak sekretów w repozytorium.

## 2. Test instalacji

- czysta instalacja,
- ponowna instalacja,
- odinstalowanie,
- aktualizacja wersji,
- brak konfliktu z innymi modułami.

## 3. Testy Back Office

- otwarcie panelu,
- uprawnienia pracownika,
- filtrowanie,
- sortowanie,
- paginacja,
- rozwijanie produktów,
- ustawienia kolumn,
- zapis preferencji.

## 4. Testy przesyłek

- rekord z FID i numerem listu,
- rekord bez FID,
- rekord bez numeru listu,
- wiele paczek,
- minimalna waga,
- COD TAK/NIE,
- błąd danych klienta,
- błąd API,
- timeout API,
- powtórny druk,
- powtórne nadanie.

## 5. Testy wydruku

- A6,
- A4,
- wiele etykiet,
- etykieta + lista produktów,
- przekroczenie limitu batch,
- brak numeru listu,
- ponowny wydruk.

## 6. Testy bezpieczeństwa

- CSRF,
- brak uprawnień,
- manipulacja ID zamówienia,
- manipulacja ID przesyłki,
- XSS w danych klienta,
- SQL injection w filtrach,
- logowanie bez sekretów.

## 7. Test ZIP

- jeden katalog główny `dpdpackoffice/`,
- separator `/`,
- brak podwójnego katalogu,
- brak `modules/dpdpackoffice/`,
- brak plików testowych i sekretów,
- poprawna instalacja z ZIP.

## Raport testów

Każdy test musi mieć:

- nazwę,
- środowisko,
- dane wejściowe,
- oczekiwany wynik,
- wynik rzeczywisty,
- status PASS/FAIL,
- dowód lub log,
- ograniczenia.
