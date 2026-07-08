# WORKFLOW GITHUB

## Gałęzie

- `main` — stabilna dokumentacja i zaakceptowany kod,
- `feature/dpdpackoffice-*` — praca nad funkcją,
- `fix/dpdpackoffice-*` — poprawki,
- `release/dpdpackoffice-*` — przygotowanie wydania.

## Commit

Przykłady:

- `docs(dpdpackoffice): add project handoff`
- `feat(dpdpackoffice): add shipment list`
- `fix(dpdpackoffice): validate admin token`
- `test(dpdpackoffice): add install checklist`
- `build(dpdpackoffice): add zip validation`

## Pull request

PR powinien zawierać:

- cel,
- zakres,
- zmienione pliki,
- testy,
- wyniki,
- ryzyka,
- screenshoty,
- kryteria akceptacji,
- artefakt ZIP.

## Release

Każdy release powinien mieć:

- tag,
- changelog,
- checksum,
- ZIP,
- raport testów,
- commit źródłowy.
