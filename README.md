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

## Setup for New Users

### Installing Git (First Time)

If you've never used Git before, you'll need to install it:

**macOS:**
```bash
# Using Homebrew (recommended)
brew install git

# Or download from https://git-scm.com/download/mac
```

**Windows:**
- Download Git from [git-scm.com](https://git-scm.com/download/win)
- Run the installer (use default settings)

**Linux:**
```bash
# Ubuntu/Debian
sudo apt-get install git

# Fedora
sudo dnf install git
```

**Configure Git** (first time only):
```bash
git config --global user.name "Your Name"
git config --global user.email "your.email@example.com"
```

**Verify installation:**
```bash
git --version
```

### Installing LaTeX (First Time)

You need a LaTeX distribution to compile the handbook:

**macOS:**
- Download and install [MacTeX](https://www.tug.org/mactex/) (3.9 GB)
- Or install BasicTeX (smaller, 80 MB): `brew install basictex`

**Windows:**
- Download and install [MiKTeX](https://miktex.org/download)
- Or install [TeX Live](https://www.tug.org/texlive/windows.html)

**Linux:**
```bash
# Ubuntu/Debian
sudo apt-get install texlive-full

# Fedora
sudo dnf install texlive-scheme-full
```

**Verify installation:**
```bash
pdflatex --version
```

### Recommended Text Editors

For editing `.tex` files, we recommend:

- **[Visual Studio Code](https://code.visualstudio.com/)** with [LaTeX Workshop extension](https://marketplace.visualstudio.com/items?itemName=James-Yu.latex-workshop) (cross-platform, beginner-friendly)
<!-- - **[Sublime Text](https://www.sublimetext.com/)** with LaTeXTools package
- **[TeXShop](https://pages.uoregon.edu/koch/texshop/)** (macOS only, comes with MacTeX)
- **[Overleaf](https://www.overleaf.com/)** (online, no installation needed, but requires syncing with Git) -->

## Building the PDF

### Requirements

- LaTeX distribution (TeX Live, MacTeX, or MiKTeX)
- Required packages: extarticle, fontsize, geometry, xcolor, fancyhdr, tcolorbox, tikz, titlesec, tocloft, enumitem, parskip, booktabs, graphicx, float, hyperref

### Compile

```bash
pdflatex main.tex
```

The output will be generated as `main.pdf` (61 pages).

### Collaborating with Git

#### First Time Setup

Clone the repository to your local machine:

```bash
git clone https://github.com/fanghe-ma/atacama-handbook.git
cd atacama-handbook
```

#### Getting Private Assets

Some files are **not tracked by git**:
- `assets/participants/`
- `private_data/`

**To build the PDF or make edits, reach out via email to these assets.** Place them in the appropriate directories before compiling.

#### Making Changes

1. **Pull the latest changes** before you start working:
   ```bash
   git pull origin main
   ```

2. **Make your edits** to the `.tex` files in your text editor or IDE

3. **Test your changes** by building the PDF:
   ```bash
   pdflatex main.tex
   ```
   Review the output `main.pdf` to ensure your changes look correct.

4. **Stage your changes**:
   ```bash
   git add .
   ```
   Or stage specific files:
   ```bash
   git add sections/01-people.tex
   ```

5. **Commit your changes** with a descriptive message:
   ```bash
   git commit -m "Update participant bios for 2026 cohort"
   ```

6. **Push your changes** to the remote repository:
   ```bash
   git push origin main
   ```

#### Common Workflows

**Updating participant bios:**
```bash
git pull origin main
# Edit sections/01-people.tex
pdflatex main.tex  # Test your changes
git add .
git commit -m "Add bio for new participant"
git push origin main
```

**Adding new images:**
```bash
git pull origin main
# Add image to assets/photos/
# Give the image an informative name, then recruit the help of 
# LLMs to insert them into the appropriate section
# Reference it in the appropriate section file
pdflatex main.tex  # Test your changes
git add .
git commit -m "Add landscape photo to Place section"
git push origin main
```

#### Tips

- Always pull before starting work to avoid merge conflicts
- Commit frequently with clear, descriptive messages
- Test your changes by building the PDF before pushing
- If you encounter conflicts, reach out to the team for help

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
├── assets/
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

Place images in `assets/photos/` and reference them in the appropriate section file:

```latex
\includegraphics[width=0.85\linewidth]{assets/photos/image_name.jpg}
```

## License

Created for Wharton Leadership Ventures. All rights reserved.

## Notes

- Build artifacts (`.aux`, `.log`, `.out`, etc.) are excluded via `.gitignore`
- Images are sourced from Pexels, Unsplash, and Wikimedia Commons (free to use)
