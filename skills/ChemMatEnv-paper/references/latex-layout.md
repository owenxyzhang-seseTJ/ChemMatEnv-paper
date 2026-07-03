# LaTeX Layout Diagnostics

Use this protocol when the user asks to fix placement problems in a materials/chemistry LaTeX manuscript — loose or sparse pages, stranded section headings, figures that do not fill the page or split across pages, "Float too large" errors, multi-panel figure arrangement, or sparse Supplementary Information. This content is adapted from the nature-polishing skill's LaTeX layout reference; it is ~95% universal. Skip this file when the task is prose-only.

## Diagnosis Workflow

1. **Compile** the manuscript and read the `.log` file for three signals:
   - `Float too large for page by Xpt`
   - `Overfull \vbox`
   - `undefined references`
2. **Render pages to contact sheet** (PNG or screenshot grid). Visually inspect every page. Do not judge layout from `.tex` source alone.
3. **Measure figure aspect ratios** from source PDFs. A figure at 4:1 (wide XRD pattern strip) will leave 40-50% empty space on a portrait page.

## Fix Patterns

### Loose Float Pages

Floats that pack at the top with slack below: the page is top-aligned by default but the glue between floats is large. Redefine the float-page glue so floats pack tightly from the top and slack collects only at the very bottom:

```latex
\makeatletter
\setlength{\@fptop}{0pt}
\setlength{\@fpsep}{8pt plus 2pt}
\setlength{\@fpbot}{0pt plus 1fil}
\makeatother
```

Also tune the float-placement fractions: `\topfraction=0.9`, `\bottomfraction=0.9`, `\textfraction=0.1`, `\floatpagefraction=0.7`.

### Wide-and-Short Figures (Common in Materials Papers)

An XRD pattern or wide TEM image at 3:1-4:1 aspect ratio wastes 40-50% of the page. The fix is regenerating the figure to a target aspect ratio of **1.9:1 to 2.2:1** (e.g., in matplotlib, change `figsize=(8,4)` to `figsize=(8,3.8)`). Rules:
- Verify that the redraw is faithful to the data.
- Only touch the SI/working branch, not the final publication source.
- Font size is set by display width, not figure height — do not squish.
- Account for caption space (~3-5 lines) when sizing the figure.

### Do Not Rotate to Landscape (Nature/NatComms)

Nature and Nature Communications prefer upright figures. For other materials/chemistry journals (JACS, Angewandte, Adv. Mater., EES), landscape figures are more tolerated but still draw attention to aspect-ratio problems. Prefer a taller redraw over `\rotatebox` or `sidewaysfigure`.

### Stranded Section Headings

Occurs when a float backlog pushes figures pages later while headings stack up without their figures. Fix: bind each "heading + figure" pair into a unit using `\clearpage` + `[H]` placement, and size figures to share a page with their heading and caption. Also pin the preceding section's trailing figure with `\clearpage`.

### Multi-Panel Figures

Prefer a vertical single-column stack over a 2×2 grid — this uses page space more efficiently and avoids small, hard-to-read panels. For small `Float too large` errors (a few points), try shaving 2% from figure width or reducing inter-panel `\vspace` before touching the figure source.

### `[H]` and `placeins` Sharp Edges

- `[H]` is safe only when paired with `\clearpage` and the figure is sized to share a page with its heading/caption.
- `\usepackage{placeins}` with `\FloatBarrier` can strand headings if figures are too tall to fit after the barrier.
- Do not blanket `\clearpage` every section — use it only for figure-heavy sections (Results, SI).

### Supplementary Information Density

Materials papers often have dense SI with many characterization figures. For SI:
- Use `\clearpage` + `[H]` to keep each figure with its caption.
- Stack related figures (e.g., XRD + SEM of the same sample) vertically in one float.
- For very small figures (e.g., single NMR spectra), combine 2-3 into one float with subfigures.

### Quick Checklist

- [ ] Log is clean of `Float too large` and `Overfull \vbox`
- [ ] Every float page is visually full or has controlled slack at bottom only
- [ ] No stranded headings — each heading has its figure within one page turn
- [ ] Multi-panel figures use vertical stacking where possible
- [ ] Figure aspect ratios are in the 1.9:1-2.2:1 range, or justified exceptions
- [ ] SI is dense but readable — no single-panel figures on an otherwise empty page
- [ ] `\clearpage` used only where needed, not blanket-applied
- [ ] Before-and-after PDF renders confirm the fixes visibly improved the pages
