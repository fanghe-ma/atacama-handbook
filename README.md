# Atacama Field Guide

Field guide and handbook for Wharton Leadership Ventures' Atacama Desert expedition (March 2026).

## Overview

This handbook provides essential information for participants in the Atacama Desert leadership venture, including:

- Team member profiles (guides, venture facilitators, participants)
- Background on the Atacama Desert (geography, history, flora, fauna, astronomy)
- Technical and logistical information (weather, health, safety, travel details)
- Leadership frameworks (NOLS model, debriefing guides)
- Case studies for discussion
- Conflict management strategies
- Daily reflection prompts and personal notes pages

## Building the PDF

### Requirements

- LaTeX distribution (TeX Live, MacTeX, or MiKTeX)
- Required packages: extarticle, fontsize, geometry, xcolor, fancyhdr, tcolorbox, tikz, titlesec, tocloft, enumitem, parskip, booktabs, graphicx, float, hyperref

### Compile

```bash
pdflatex main.tex
```

The output will be generated as `main.pdf` (61 pages).

## Project Structure

```
atacama-handbook/
├── main.tex                    # Main document controller
├── preamble.tex               # Document styling and packages
├── environments.tex           # Custom callout boxes (safety, fieldtip, reflection)
├── bibliography.bib           # Bibliography entries (optional)
├── sections/
│   ├── 00-frontmatter.tex    # Title page and table of contents
│   ├── 01-people.tex         # Guide, VF, and participant bios
│   ├── 02-place.tex          # Atacama background and context
│   ├── 03-technical.tex      # Logistics, safety, knots, Leave No Trace
│   ├── 04-leadership.tex     # NOLS Leadership Model
│   ├── 05-cases.tex          # Case studies
│   ├── 06-provokers.tex      # Conflict management and AAR
│   └── 07-reflection.tex     # Pre/post reflections, daily prompts, notes
├── figures/
│   └── photos/               # Images (landscapes, wildlife, knots, maps, etc.)
└── sample/                   # Reference materials
```

## Color Palette

The handbook uses an Atacama-inspired color scheme:

- **atacamaSand**: RGB(196,167,125) - warm sandy beige
- **atacamaTerracotta**: RGB(168,92,60) - reddish brown for headings
- **atacamaSage**: RGB(109,120,92) - muted green
- **atacamaSky**: RGB(91,124,153) - dusty blue
- **atacamaDark**: RGB(61,44,41) - dark brown
- **atacamaCream**: RGB(248,244,238) - off-white background


## Customization

### Updating Participant Information

Edit `sections/01-people.tex` to update guide, VF, and participant bios.

### Modifying Daily Reflections

Edit `sections/07-reflection.tex` to:
- Change the number of daily reflection pages (currently 7 days)
- Update "Question of the day" prompts (currently placeholders for LOD to set)
- Adjust the number of lined pages in Personal Notes section

### Adding Images

Place images in `figures/photos/` and reference them in the appropriate section file:

```latex
\includegraphics[width=0.85\linewidth]{figures/photos/image_name.jpg}
```

## License

Created for Wharton Leadership Ventures. All rights reserved.

## Notes

- Build artifacts (`.aux`, `.log`, `.out`, etc.) are excluded via `.gitignore`
- Images are sourced from Pexels, Unsplash, and Wikimedia Commons (free to use)
