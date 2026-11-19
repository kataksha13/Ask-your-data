# Ask your data

A single-page data exploration app with a South Indian look (kolam, lotus and Tanjore-style gold and maroon). Load a table, describe what you want in plain English, build charts like a BI dashboard, and generate an analyst-style report.

The app is one file, `index.html`. It needs no server, no account and no API key.

## Features

**Explore**
- Load a CSV or TSV file, paste CSV text, or try the built-in sample.
- Type requests in plain English. The built-in engine understands:
  - Cleaning: title case, upper or lower case, trim spaces, remove duplicates, fill empty cells (with the median, mean, most common value or a value you give), remove rows with empty cells.
  - Reshaping: sort, filter (over, under, between, is, contains), rename or drop a column.
  - Questions: "average rating by genre", "top 5 by rating", "summarize each number column", "how many missing values".
- Changed cells are highlighted, every step is listed with its code, and you can undo steps.

**Dashboard**
- Bar, horizontal bar, line, pie, doughnut and scatter charts (Chart.js).
- Key number cards and a filter that applies to every chart.
- Build a chart from the menus, or type something like "pie chart of genre" or "average rating by genre as a bar chart".

**Report**
- Executive summary, key findings, data quality checks, column profiles, relationships between numbers, and recommendations.
- Download the report as Markdown.

## Host it (GitHub Pages)

1. Upload `index.html` and `README.md` to a repository.
2. Go to **Settings → Pages**, choose **Deploy from a branch**, set branch `main` and folder `/ (root)`, then save.
3. Your site appears at `https://YOUR-USERNAME.github.io/REPO-NAME/`.

## Optional: connect a real AI model

The built-in engine handles common requests but not free-form wording. To let an AI model understand any request and write the report text, deploy `worker.js` (a small Cloudflare Worker that holds your Anthropic API key) and put its URL in `index.html` where it says `var AI_ENDPOINT="";`. API use is paid, so set a spending limit in the Anthropic console. Never put an API key in `index.html`.

## Privacy

Your table is processed in the browser and never leaves your device unless you connect an AI endpoint.

## Built with

- Plain HTML, CSS and JavaScript
- [Chart.js](https://www.chartjs.org/) 4.4.1 from cdnjs
- Google Fonts: Noto Serif Tamil and Catamaran
