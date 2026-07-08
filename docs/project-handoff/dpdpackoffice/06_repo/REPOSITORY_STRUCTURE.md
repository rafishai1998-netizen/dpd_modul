# PROPONOWANA STRUKTURA REPOZYTORIUM

```text
7dejv-prestashop/
├─ 01_modules/
│  ├─ dpdpackoffice/
│  │  ├─ src/
│  │  ├─ controllers/
│  │  ├─ views/
│  │  ├─ sql/
│  │  ├─ docs/
│  │  ├─ tests/
│  │  ├─ tools/
│  │  ├─ build/
│  │  └─ README.md
│  ├─ dpdshipmvp/
│  └─ orderpanelmvp/
├─ docs/
│  └─ project-handoff/
│     └─ dpdpackoffice/
├─ artifacts/
│  └─ dpdpackoffice/
│     ├─ test/
│     └─ release/
├─ tools/
│  └─ validate-module-zip.*
├─ CHANGELOG.md
├─ DECISIONS.md
└─ README.md
```

## Zasady

- kod modułu nie może być mieszany z ZIP-ami,
- ZIP-y trafiają do `artifacts/`,
- dokumentacja przekazania trafia do `docs/project-handoff/`,
- testowe ZIP-y i release ZIP-y muszą być rozdzielone,
- każdy artefakt musi wskazywać commit źródłowy.
