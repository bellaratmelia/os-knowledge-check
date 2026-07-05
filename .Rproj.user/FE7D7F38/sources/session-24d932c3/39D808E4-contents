# Open Science & Scholarly Publishing — Self-Assessment Quiz

A static, self-assessment quiz on open science and scholarly publishing, built
with [Quarto](https://quarto.org) and Observable JS (OJS). The whole question bank lives in one CSV file, so
you can add or edit questions without touching any code.

- **Audience:** scholarly communications librarians (and researchers, research
  infrastructure providers, and technologists in the same space).
- **No backend:** no server, no database, no accounts. Everything runs in the
  browser; a page refresh resets the session.
  
---

## Repository layout

```
.
├── _quarto.yml            # Quarto project + website configuration
├── index.qmd              # The quiz page (landing → questions → summary)
├── about.qmd              # Background, levels, areas, and sourcing notes
├── styles.css             # Styles for the quiz component
├── data/
│   └── questions.csv       # THE QUESTION BANK — single source of truth
├── .github/
│   └── workflows/
│       └── publish.yml     # GitHub Action to build & deploy to GitHub Pages
└── README.md
```

## Add or edit questions

Open **`data/questions.csv`** in a spreadsheet application or a text editor and
add one row per question. Commit and push — that's the entire workflow.

### Column reference

| Column | Required | Description |
|---|---|---|
| `id` | yes | Unique question ID (e.g. `PID-012`). |
| `level` | yes | Exactly one of: `Beginner`, `Intermediate`, `Expert`, `Master`. |
| `area` | yes | The primary topic area. Must match one of the areas below **exactly**. |
| `question` | yes | The question text. |
| `option_a` … `option_e` | yes | The five answer options. Provide all five. |
| `correct_option` | yes | The letter of the correct option: `a`, `b`, `c`, `d`, or `e`. |
| `explanation_correct` | yes | Why the correct answer is correct (shown after answering). |
| `explanation_incorrect` | recommended | Why common wrong answers are wrong (shown when the user is wrong). |
| `source_url` | optional | Link to authoritative further reading. Leave blank if none. |
| `review_note` | optional | Internal note flagging a fact to re-verify. **Never shown to users.** |

### The fixed topic areas

The `area` value must be one of these strings (they drive the topic checkboxes):

```
Persistent Identifiers
Research Data Management
Open Access
Research Assessment & Metrics
Research Integrity
Reproducibility & Open Methods
Scholarly Infrastructure & Organizations
Preprints & Peer Review
Open Source & Software
Policy & Funder Mandates
```

If you add a question whose `area` is not in this list, it is **hidden** and a
warning is logged to the browser console. To introduce a brand-new area, add it
to the `AREA_ORDER` array near the top of the quiz cell in `index.qmd`.

### CSV formatting tips

- The file is UTF-8. Any field containing a comma, quote, or line break **must
  be wrapped in double quotes**; a double quote inside a quoted field is escaped
  by doubling it (`""`). Spreadsheet apps do this automatically on export — the
  main pitfall is hand-editing.
- Vary which option holds the correct answer (don't always use the same letter).
- Aim for exactly five options per question; the UI expects five.


## Content accuracy

Questions were written from the referenced organisations' own documentation and
policy pages, and each row records a `source_url`. Rows with a `review_note`
value flag facts worth re-verifying before wider publication (e.g. figures that
grow over time, or terms whose definitions are contested). Corrections are
welcome via issues or pull requests to `data/questions.csv`.

## License

Content (the CSV) under **CC BY 4.0** and code under **MIT**. Add
`LICENSE` files to confirm before publishing.