# PROTEUS Tool Documentation and Research Journal

The `source/` directory contains the documentation for the proteus-rs-pipeline tool. So far, this includes:

- `source/sa/`: **Short Answer (control-structure)** documentation (service, roadmap, rollout, framing).
- `source/dnd/`: **Drag-and-Drop** documentation (service, framing, reference page, journal).
- `source/paper1/`: the draft manuscript for the first paper (separate from the journals).

## Status: _In flux_
> This is an active research journal. Its content evolves as the services are built out, so chapters may describe 
> work that is planned or partially landed.

## Documentation Layout

```text
prs-pipeline-docs/
├── assets/                 # Non-PreTeXt resources (e.g., figures)
├── general-references/     # Audits, worked examples, and other reference notes
├── publication/            # PreTeXt publication configuration files
├── source/                 # PreTeXt source (*.ptx files)
│   ├── sa/                 # PreTeXt book: Short Answer (SA) docs
│   │   ├── bookends/       # SA front/back matter, docinfo, and the glossary.
│   │   ├── planning/       # SA planning memos (not part of the book build)
│   │   ├── ch-*.ptx        # SA chapters (imported by sa-journal.ptx)
│   │   └── sa-journal.ptx  # SA documentation entry point (the journal)
│   ├── dnd/                # PreTeXt book: Drag-and-Drop (DND) docs
│   │   ├── bookends/       # DND front/back matter, docinfo, and the glossary.
│   │   ├── ch-*.ptx        # DND chapters (imported by dnd-journal.ptx)
│   │   └── dnd-journal.ptx # DND documentation entry point
│   └── paper1/             # Draft manuscript for the first paper
│       └── paper1-manuscript.ptx  # Manuscript entry point
├── site/                   # Static landing page for the GitHub Pages deployment
└── README.md               # This document
```

The PreTeXt project manifest is `project.ptx` at the repository root; it points
its `source`, `publication`, `output-dir`, `stage`, and `site` paths into this
directory.

## Deploying to GitHub Pages

The project manifest (`project.ptx` at the repository root) declares deploy
targets (currently `sa`, `sa-pdf`, `dnd`, `dnd-pdf`, `paper1`, and
`paper1-pdf`, each with a `deploy-dir`) and points `site="site"` at the
landing page. Running

```sh
pretext build sa
pretext build sa-pdf
pretext build dnd
pretext build dnd-pdf
pretext deploy
```

stages each built target into its `deploy-dir` under `output/deployed/`
(the manifest's `stage` directory), copies the contents of `site/` over
the top as the site root, and publishes the staged tree to the `gh-pages`
branch. Because `site/` exists and contains no `site.ptx`/`site.json`,
the PreTeXt CLI uses its "static" deployment strategy: `site/index.html`
becomes the landing page verbatim, with the SA HTML book served from `sa/`,
the DnD HTML book from `dnd/`, and their PDFs from `pdf/sa-journal.pdf` and
`pdf/dnd-journal.pdf`. The `paper1` targets are optional in this workflow —
`pretext deploy` stages only targets that have been built, so add
`pretext build paper1` / `pretext build paper1-pdf` when the draft should
deploy too; its HTML is served from `paper1/` and its PDF from
`paper1-pdf/paper1.pdf` (not under `pdf/`). Use `pretext deploy --stage-only`
to stage locally without pushing.