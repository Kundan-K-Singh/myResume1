# Resume

LaTeX source for Kundan Kumar's resume.

## Build

From this directory:

```sh
pdflatex -interaction=nonstopmode resume.tex
```

Output: `resume.pdf`.

The `-interaction=nonstopmode` flag prevents LaTeX from pausing on warnings.

### Watch mode (optional)

Auto-rebuild on every save:

```sh
latexmk -pdf -pvc resume.tex
```

Requires `latexmk` (usually bundled with TeX Live).

## Files

| File | Purpose |
| --- | --- |
| `resume.tex` | Source — edit this |
| `resume.pdf` | Built output |
| `.gitignore` | Ignores LaTeX build artifacts (`.aux`, `.log`, `.out`, etc.) and `.DS_Store` |

Build artifacts (`resume.aux`, `resume.log`, `resume.out`) are regenerated on every build and are gitignored.

## Editing notes

- The `\resumeItem{Title}{Body}` macro at the top of `resume.tex` is what produces each bullet — use it consistently for spacing to behave.
- LaTeX special characters that need escaping in bullet text: `&` → `\&`, `%` → `\%`, `$` → `\$`, `#` → `\#`, `_` → `\_`.
- Use `---` for em dashes.
- For "approximately" use `$\sim$`.

## Troubleshooting

- **Build fails with `Undefined control sequence`:** check for unescaped `&` or `%` in your edits.
- **Visible gap between bullets:** the `\resumeItem` macro applies a `\vspace{-2pt}` after each item to keep them tight. If a gap appears, the previous bullet's last line likely wrapped awkwardly — try shortening it slightly.
- **PDF viewer shows old version:** close and reopen the file; some viewers cache.
