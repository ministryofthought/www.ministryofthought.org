# Repository structure

```text
.
├── .github/
│   └── workflows/
│       └── azure-static-web-apps.yml
├── archetypes/
├── assets/
│   └── css/
├── content/
│   ├── articles/
│   ├── pages/
│   └── talks/
├── layouts/
│   ├── _default/
│   ├── partials/
│   ├── taxonomy/
│   └── talks/
├── static/
│   ├── icons/
│   ├── images/
│   └── staticwebapp.config.json
├── .gitignore
├── hugo.toml
└── README.md
```

Notes:

- `static/staticwebapp.config.json` is copied into the site root on build, so Azure can use it.
- `public/` is build output and should not be committed.
- Layouts are intentionally simple and easy to refactor.
