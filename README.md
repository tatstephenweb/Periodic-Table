# Periodic Table Trainer

An interactive periodic table for learning the elements. It's a single HTML file with no dependencies, no build step and no backend. Open it in a browser and it works.

## Features

- **Explore:** tap any of the 118 elements to see its name, symbol, atomic number, category, period and group.
- **Find it:** you're given an element name and have to tap it on the table. Names are hidden, so you learn the layout and symbols.
- **Quiz:** you're shown a symbol and atomic number and pick the correct name from four options.
- **Score tracking** for Find it and Quiz.
- **Colour-coded categories** (alkali metals, halogens, noble gases and so on) with a legend.
- **Responsive and theme-aware:** the table scrolls sideways on small screens, and light and dark modes follow the system setting.

## Getting started

1. Download `periodic-table.html`.
2. Open it in any modern browser.

That's it. To host it, upload the file to any static host (GitHub Pages, Netlify, Render static site, or cPanel/InfinityFree) or drop it into an existing Flask or PHP project as a static page.

## How it works

All element data lives in one comma-separated string called `RAW` near the bottom of the file, in atomic number order:

```
H Hydrogen,He Helium,Li Lithium, ...
```

For each element, the script works out three things:

- **Category** from the atomic number (`cat()` function)
- **Grid position** on the table (`pos()` function)
- **Period and group** for the detail panel

The table is a CSS grid with 18 columns. The lanthanides and actinides sit in rows 9 and 10, below the main table.

## Customising

| To change | Edit |
|---|---|
| Colours and theme | CSS variables at the top of the file (`:root`) |
| Category names | The `CATS` object |
| Which elements belong to which category | The `cat()` function |
| Number of quiz options | The `wrong` loop in `next()` |
| Delay before the next question | The `setTimeout` values in `answerQuiz()` and `onCell()` |

## Project structure

```
periodic-table.html   # markup, styles and script in one file
README.md
```

## Roadmap

- [ ] Reverse quiz (name to symbol)
- [ ] Review mode that repeats missed elements
- [ ] Atomic mass, electron configuration and state at room temperature
- [ ] Streaks and saved progress
- [ ] Timed mode and per-category practice

## Notes

- Spellings follow IUPAC and British usage (aluminium, caesium, sulfur).
- Categories follow a common textbook convention. Sources differ on a few elements, such as polonium and astatine, so adjust `cat()` if your syllabus groups them differently.
- Atomic number, symbol and name are the only data stored, so there's nothing to keep up to date.

## Licence

Free to use and modify. Add your preferred licence (for example MIT) before publishing.
