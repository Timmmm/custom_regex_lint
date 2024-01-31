# Custom Regex Lint

A pre-commit hook to ban custom regexes from your code, for example you might want to ban `REMOVE THIS` so that you don't accidentally commit temporary debugging code.

Regexes use [the Rust `regex` crate](https://docs.rs/regex/latest/regex/). You can try them on [regex101.com](https://regex101.com/). The regexes are multiline so `^` and `$` match the beginning and end of lines. They are case sensitive.

## Integrating

Add this to your `.pre-commit-config.yaml`:

```
  - repo: https://github.com/timmmm/custom_regex_lint
    rev: v1.0.0
    hooks:
      - id: custom_regex_lint
        args:
        - "--error-regex"
        - "\\bREMOVE THIS\\b"
        - "--error-regex"
        - "\\bDO NOT COMMIT\\b"
```
