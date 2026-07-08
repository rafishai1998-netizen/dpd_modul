# RYZYKA I BEZPIECZEŃSTWO

## Ryzyka krytyczne

1. Ponowne nadanie tej samej przesyłki.
2. Ponowny wydruk bez ostrzeżenia.
3. Ujawnienie loginu, hasła lub tokenu DPD.
4. Automatyczne wywołanie API przy otwarciu panelu.
5. Błędne przypisanie listu do zamówienia.
6. Zapis etykiet w katalogu publicznym.
7. Brak kontroli uprawnień pracownika.
8. Operacje zbiorcze na błędnych rekordach.
9. Konflikt z istniejącym modułem DPD.
10. Rozjazd pomiędzy FID, numerem listu i rekordem zamówienia.

## Zabezpieczenia

- jawne potwierdzenia operacji nieodwracalnych,
- tokeny i CSRF,
- idempotencja operacji,
- log operacyjny,
- identyfikator korelacyjny,
- transakcje bazodanowe tam, gdzie potrzebne,
- walidacja przed wywołaniem API,
- bezpieczny magazyn plików,
- minimalne uprawnienia,
- brak sekretów w komunikatach użytkownika.

## Ważna decyzja

API DPD może być wywoływane wyłącznie po świadomej akcji operatora.
