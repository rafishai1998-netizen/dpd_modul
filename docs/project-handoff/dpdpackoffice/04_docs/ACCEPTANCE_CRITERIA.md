# KRYTERIA AKCEPTACJI

## Instalacja

- moduł instaluje się bez błędu,
- moduł odinstalowuje się bez błędu,
- nie pozostawia uszkodzonych tabel,
- tworzy zakładkę Back Office,
- respektuje uprawnienia pracowników.

## Bezpieczeństwo

- wszystkie akcje modyfikujące stan wymagają tokenu,
- formularze mają ochronę CSRF,
- wejścia są walidowane,
- brak SQL injection,
- brak XSS,
- brak sekretów w logach,
- brak plików etykiet w publicznym katalogu modułu,
- brak automatycznych wywołań API po wejściu do panelu.

## Funkcjonalność

- tabela wyświetla istniejące przesyłki,
- filtry działają poprawnie,
- niewydrukowane mogą być sortowane na górze,
- waga nie może spaść poniżej 1 kg,
- operacje zbiorcze pomijają rekordy bez numeru listu,
- limit operacji zbiorczych jest respektowany,
- ponowny wydruk wymaga potwierdzenia,
- ponowne nadanie wymaga potwierdzenia,
- historia zapisuje każdą operację,
- błędy API są czytelne i nie ujawniają sekretów.

## Jakość

- brak modyfikacji core,
- brak override bez jawnej decyzji,
- kod zgodny z architekturą PrestaShop 9,
- brak duplikacji istniejących funkcji,
- dokumentacja instalacji i konfiguracji,
- poprawny ZIP z jednym katalogiem głównym modułu.

## Artefakty końcowe

- kod modułu,
- ZIP testowy,
- ZIP release,
- raport testów,
- lista zmienionych plików,
- raport błędów i ograniczeń,
- instrukcja instalacji,
- changelog.
