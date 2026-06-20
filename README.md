# NABTA Graduation Project Documentation

This folder contains the reorganized LaTeX source for the NABTA graduation project report.

## VS Code Compilation

1. Install MiKTeX and the LaTeX Workshop VS Code extension.
2. Open this folder in VS Code.
3. Open `main.tex`.
4. Run `LaTeX Workshop: Build with recipe`.
5. Select `XeLaTeX + BibTeX`.

The workspace recipe does not use `latexmk`, Perl, or `makeglossaries`.
Generated files are written to the `build/` folder.

## Overleaf Compilation

Set the compiler to **XeLaTeX** and compile normally. The glossary uses no-index mode, so no separate MakeGlossaries step is required.

## Main File

Use `main.tex` as the root document.

## Placeholder Policy

Search the source for `TODO:` to find visuals that still need final exported files, including logos, diagrams, screenshots, graphs, and comparison charts.

## Adding Logos

Add transparent PNG files to `assets/logos/` with these names:

- `university_logo.png`
- `faculty_logo.png`
- `project_logo.png`

The cover detects them automatically. No LaTeX edit is required.

## Adding Figures, Screenshots, and Graphs

The report uses this reusable command:

```latex
\projectfigure[0.9\textwidth]
  {assets/figures/example.png}
  {8cm}
  {Professional figure caption}
  {fig:example}
```

The optional first value is maximum width, the second argument is the asset
path, the third is maximum height, the fourth is the caption, and the fifth is
the reference label. Use `\figref{fig:example}` in the text.

If the file does not exist, a styled placeholder is printed automatically. PNG
and JPG are best for screenshots; PDF is best for vector diagrams and graphs.
Never use spaces or special characters in asset filenames.

Exact expected filenames are listed in the README file inside each asset
folder. After adding an image, rebuild with the `XeLaTeX + BibTeX` recipe.
