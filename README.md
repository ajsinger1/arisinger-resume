# Resume

LaTeX source for my professional resume, compiled with XeLaTeX.

## Building

### Prerequisites

- XeLaTeX (via TeX Live or similar)
- TeX Gyre fonts (Termes, Adventor)

On macOS (via [Homebrew](https://brew.sh)):

```bash
brew install --cask mactex
```

Then install the required TeX Gyre fonts:

```bash
sudo tlmgr install tex-gyre
```

On Debian/Ubuntu:

```bash
sudo apt-get install texlive-xetex texlive-fonts-extra
```

### Compile

```bash
make
```

Or directly:

```bash
xelatex resume.tex
```

## Customization

The resume uses custom colors defined at the top of `resume.tex`:

| Color | Hex | Usage |
|---|---|---|
| `textcolor` | `#2b2b2b` | Body text |
| `headingcolor` | `#701112` | Section headings |
| `linkcolor` | `#506266` | Hyperlinks |
| `highlightcolor` | `#F5DD9D` | Highlights |

Fonts can be changed by modifying the `\setmainfont` and `\setsansfont` declarations.
