# Osaka AI integration

This repository is intended to be used as a dependency of `machida111/osaka-ai`.

The recommended setup is to keep `osaka-ai` as the main repository and attach `codex` as a submodule.

## Recommended structure

```text
osaka-ai/
├── .git/
├── vendor/
│   └── codex/
│       └── ...
├── src/
└── ...
```

## Add this repo as a submodule from `osaka-ai`

Run the following from a local clone of `machida111/osaka-ai`:

```bash
git submodule add https://github.com/machida111/codex.git vendor/codex
git add .gitmodules vendor/codex
git commit -m "Add codex as a submodule"
git push origin HEAD
```

If you prefer a different folder name:

```bash
git submodule add https://github.com/machida111/codex.git third_party/codex
```

## Update the submodule

```bash
cd osaka-ai
git submodule update --init --recursive
```

To pull the latest `codex` changes:

```bash
cd osaka-ai/vendor/codex
git pull origin main
cd ../..
git add vendor/codex
git commit -m "Update codex submodule"
git push origin HEAD
```

## Why this layout

- `osaka-ai` remains the primary repo for the project.
- `codex` remains a separate, versioned dependency.
- The connection is explicit and easy to review in pull requests.

## Notes

This repository can also be used independently, but when working in `machida111/osaka-ai`, it is best treated as a submodule dependency rather than as the main project root.
