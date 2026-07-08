# DPD szybkie nadawanie

Repozytorium projektu dla modułu PrestaShop usprawniającego obsługę nadań DPD w back office sklepu RaFish.

## Cel

Celem projektu jest stworzenie roboczego panelu do obsługi przesyłek DPD: kolejki zamówień, nadawania, wydruku etykiet, obsługi COD, wielopaczek, błędów danych, historii oraz diagnostyki.

## Założenie

Moduł ma być lekką nakładką roboczą na oficjalny moduł DPD / `dpdshipping`, o ile pozwoli na to jego struktura techniczna. Nie zakładamy przebudowy rdzenia PrestaShop.

## Materiały projektowe

Główne materiały z paczki przekazania znajdują się w katalogu:

`docs/project-handoff/dpdpackoffice/`

Najważniejsze pliki:

- `README.md` — opis paczki przekazania.
- `04_docs/PROJECT_BRIEF.md` — brief projektu.
- `04_docs/FEATURES.md` — lista funkcji.
- `04_docs/TEST_PLAN.md` — plan testów.
- `02_mockup/dpdpackoffice-makieta-v4.html` — makieta HTML panelu.
- `03_prompts/CODEX_IMPLEMENTATION_PROMPT.md` — instrukcja dla Codexa.
- `03_prompts/REPLIT_PROTOTYPE_PROMPT.md` — instrukcja dla Replit.

## Kierunek prac

1. Najpierw dopracować wygląd i workflow.
2. Potem rozbić funkcje na Issues.
3. Następnie budować małe funkcje na osobnych branchach.
4. Testować na kopii sklepu przed wdrożeniem.
