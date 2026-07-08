# PROMPT DLA CODEX

## Kontekst

Projekt: `dpdpackoffice`
Platforma: PrestaShop 9
Repozytorium GitHub jest źródłem prawdy.

## Cel

Przeanalizować repozytorium i przygotować lub rozwinąć moduł `dpdpackoffice` zgodnie z dokumentacją projektu.

## Etap 1 — audyt obowiązkowy

Najpierw:

1. sprawdź strukturę repozytorium,
2. znajdź wszystkie pliki związane z:
   - dpdpackoffice,
   - dpdshipmvp,
   - orderpanelmvp,
   - DPD,
   - etykietami,
   - FID,
   - numerem listu,
   - pakowaniem ZIP,
3. przeczytaj README, decyzje, wymagania, testy i changelog,
4. sprawdź branche, commity i PR-y,
5. zgłoś konflikty, duplikaty i brakujące dane,
6. nie zmieniaj plików przed zakończeniem audytu.

## Etap 2 — plan

Przed implementacją przygotuj:

- listę plików do utworzenia,
- listę plików do zmiany,
- architekturę modułu,
- migracje bazy,
- kontrolery,
- usługi,
- hooki,
- zabezpieczenia,
- testy,
- plan ZIP.

## Ograniczenia

- bez modyfikacji core,
- bez override, chyba że repozytorium i dokumentacja wykażą konieczność,
- bez automatycznych wywołań API po otwarciu panelu,
- bez logowania sekretów,
- bez przechowywania etykiet w publicznym katalogu modułu,
- minimalny zakres zmian,
- nie zmieniaj `dpdshipmvp` ani `orderpanelmvp`, jeśli nie jest to konieczne.

## Wymagania

Implementacja ma spełnić dokumenty:

- `04_docs/PROJECT_BRIEF.md`
- `04_docs/FEATURES.md`
- `04_docs/ACCEPTANCE_CRITERIA.md`
- `04_docs/TEST_PLAN.md`
- `04_docs/RISKS_AND_SECURITY.md`
- `04_docs/DECISIONS.md`

## Testy

Uruchom tyle testów, ile pozwala środowisko. Nie deklaruj testów, których nie wykonano.

## Artefakty

Przygotuj:

- kod modułu,
- ZIP testowy,
- raport testów,
- listę zmienionych plików,
- changelog,
- instrukcję instalacji,
- raport braków i ograniczeń.

## Raport końcowy

Raport musi zawierać:

1. zmienione pliki,
2. utworzone pliki,
3. wykonane testy,
4. niewykonane testy,
5. wyniki,
6. błędy,
7. ryzyka,
8. stan kryteriów akceptacji,
9. lokalizację ZIP,
10. następny krok.

Nie używaj ogólnego stwierdzenia „100% ukończone”, jeśli brakuje dowodów.
