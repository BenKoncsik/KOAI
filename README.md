License Notice

This project is source-available for personal, non-commercial use only.
Commercial use is not allowed without prior written permission.
Modification, redistribution, and public forking are prohibited.
See LICENSE.txt for full terms.

# KOAI

KOAI is a local-first macOS research assistant for turning a topic into a structured, traceable research workflow.

It searches the web in the background, extracts readable content from promising pages, stores everything locally in SQLite, and produces a concise synthesized report with a local or local-friendly LLM backend.

## Highlights

- Topic-driven research jobs
- Ad hoc prompts for one-off investigations
- Background browsing with `WKWebView`
- Source discovery, ranking, deduplication, and extraction
- Incremental article summaries plus final synthesis
- SQLite persistence for jobs, sources, articles, traces, and summaries
- Local model support for `llama.cpp`, `llama-server`, and `ollama`
- Hugging Face model library browsing for local-friendly models
- English and Hungarian UI localization

## What KOAI is for

KOAI is a good fit when you want to:

- research a topic without manually opening dozens of tabs
- keep the process organized and repeatable
- inspect what the app searched, opened, and extracted
- summarize multiple sources into one readable output
- keep data on your machine instead of sending it to a cloud service

KOAI is not a general-purpose browser, not a feed reader, and not a single-site scraper. It is designed around staged, topic-based research.

## How it works

1. Create or select one or more topics.
2. Start a research job from those topics or enter an ad hoc prompt.
3. KOAI builds a query plan and searches for relevant sources.
4. The app opens promising pages in a hidden browser, extracts text, and stores the results.
5. It summarizes individual articles and then combines them into a final report.
6. You can review the job history, traces, sources, and summary from the UI.

## Screens

Add screenshots here once you have them:

- Main dashboard
- Topic editor
- Research job progress
- Source and summary view

## Requirements

- macOS 14 or later
- Swift 6
- A local `llama.cpp` or `ollama` setup if you want LLM-powered summaries

If no model runtime is available, KOAI can fall back to extractive summarization.

## Local model support

KOAI can use several backends depending on your setup:

- `llama.cpp` CLI or server
- `ollama`
- extractive fallback when no model is available

The built-in model library view helps you discover GGUF-friendly models that are better suited for local Apple Silicon use.

---

# KOAI

KOAI egy helyi működésre épülő, macOS-re készült kutatóasszisztens. Egy témából strukturált, visszakövethető research folyamatot csinál: háttérben böngészik, kinyeri az olvasható tartalmat, SQLite-ba ment mindent, majd helyi vagy helyben futó LLM-mel összefoglalót készít.

## Kiemelt funkciók

- témavezérelt kutatási jobok
- ad hoc promptok egyszeri vizsgálatokhoz
- háttérben futó böngészés `WKWebView`-val
- források felderítése, rangsorolása, deduplikálása és kinyerése
- cikkenkénti összegzés és végső szintézis
- SQLite tárolás jobokhoz, forrásokhoz, cikkekhez, trace-ekhez és összefoglalókhoz
- helyi támogatás `llama.cpp`, `llama-server` és `ollama` számára
- Hugging Face modellnézet lokálisan barátságos modellekhez
- angol és magyar felület

## Mire jó

A KOAI jó választás, ha szeretnél:

- egy témát sok kézi böngészés nélkül feldolgozni
- az egész kutatási folyamatot rendezett, ismételhető módon kezelni
- visszanézni, mit keresett az app és milyen oldalakat dolgozott fel
- több forrásból egy egységes, rövid összefoglalót kapni
- az adatokat a saját gépeden tartani, nem felhőben

Nem általános böngésző, nem feed reader, és nem egyetlen webhelyre optimalizált scraper. Lépésenkénti, témavezérelt kutatásra készült.

## Működés

1. Létrehozol vagy kiválasztasz egy vagy több témát.
2. Elindítasz egy kutatási jobot ezekből a témákból, vagy megadsz egy ad hoc promptot.
3. A KOAI keresési tervet készít és releváns forrásokat keres.
4. Az app egy rejtett böngészőben megnyitja az ígéretes oldalakat, kinyeri a szöveget, és elmenti az eredményt.
5. Az egyes cikkeket összefoglalja, majd ezekből elkészíti a végső riportot.
6. A felületen visszanézheted a job előzményeit, trace-it, forrásait és az összefoglalót.

## Képernyők

Ide érdemes később képernyőképeket tenni:

- fő nézet
- téma szerkesztő
- research job állapot
- forrás- és összefoglaló nézet

## Követelmények

- macOS 14 vagy újabb
- Swift 6
- Lokális `llama.cpp` vagy `ollama` telepítés, ha LLM-alapú összegzést szeretnél

Ha nincs model runtime, a KOAI extractive fallback módban is tud működni.

## Lokális futtatás

## Helyi modellek támogatása

A KOAI több backendet is tud használni a környezetedtől függően:

- `llama.cpp` CLI vagy szerver
- `ollama`
- extractive fallback, ha nincs elérhető modell

A beépített modellnézet segít GGUF-barát modellek keresésében, különösen Apple Silicon környezetben.

## Miért ilyen az architektúra

- a `SwiftUI` natív macOS felületet ad
- a `WKWebView` beágyazott, privacy-barát böngészéshez jó
- az `SQLite` mindent helyben és tartósan tárol
- a helyi backend absztrakció miatt az app cloud modell nélkül is használható
