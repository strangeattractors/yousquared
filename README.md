# YouSquared collateral

All YouSquared customer-facing web artifacts — prototypes, reports, playbooks —
served at <https://strange-attractor.com/yousquared/>.

## Structure

```
yousquared/
├── index.html                               → /yousquared/               (landing)
├── prototype/
│   ├── index.html                           → /yousquared/prototype/     (listing)
│   ├── industry-auto-config/                → /yousquared/prototype/industry-auto-config/
│   └── scheduled-outbound/                  → /yousquared/prototype/scheduled-outbound/
├── report/    (future)
└── playbook/  (future)
```

Every subdirectory maps 1:1 to a URL segment. Folder names are the URL slug.

## Publishing a new prototype

1. Decide a short slug: `<short-name>`.
2. Create `prototype/<short-name>/` with at least an `index.html`.
3. Add a card to `prototype/index.html`.
4. Commit, push. Pages rebuilds in ~1 minute.

For prototypes actively developed in the iOS repo (like `industry-auto-config`):
the source lives on a branch of `strangeattractors/YouSquared-ios` and is
manually copied here when a version is ready to publish. See that prototype's
own `README.md` for the specific workflow. (Auto-sync GitHub Action pending.)

## Archiving old versions of a prototype

Inside a prototype folder:

```
prototype/industry-auto-config/
├── index.html                               → current version (what `/` serves)
├── 20260417-prototype-auto-config.html      → dated permalink of current
└── archive/
    └── 2026-04-16-multiscreen/              → previous version
        └── index.html
```

Pattern: promote the new file to `index.html`, keep a dated copy at root as a
stable permalink, move the previous `index.html` into `archive/<date>-<slug>/`.

## Legacy URLs

Prior to this monorepo, prototypes were served from individual repos:

| Old URL | New URL |
|---|---|
| `strange-attractor.com/industry-auto-config-prototype/` | `strange-attractor.com/yousquared/prototype/industry-auto-config/` |
| `strange-attractor.com/scheduled-outbound-prototype/` | `strange-attractor.com/yousquared/prototype/scheduled-outbound/` |

Old repos still live and redirect their root `index.html` to the new URL.
Don't link to them in anything new.
