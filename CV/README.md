# Academic CV (LaTeX)

The source code of my one-page academic Curriculum Vitae: Palatino typography, clean section rules and a toggle to adapt the layout to different international standards.

## Features

* **Boolean Logic Switch:** Toggle between a **European style** (with photo) and an **Anglo-Saxon/International style** (text-only) by changing a single variable: `\setbool{showphoto}{true/false}`.
* **Single Data Block:** Name, city, e-mail, LinkedIn and GitHub are defined once as macros (`\cvname`, `\cvemail`, `\cvgithub`, …) at the top of the file; every header and link is built from them.
* **Math Typography:** Uses `mathpazo` and `amssymb` for high-quality mathematical notation.
* **Compact Structure:** Education, Honors, Research Experience, Research Interests, Independent Study, Teaching & Other Experience and Skills, on a single page.

## How to Use

1.  Clone the repository or download `CV.tex`.
2.  Open it in your favourite LaTeX editor (Overleaf, TeXShop, VS Code) and compile it with `pdflatex`.
3.  **For the Photo Version:**
    * Place a square/portrait image named `photo.jpg` in the same directory.
    * Set `\setbool{showphoto}{true}` in the preamble.
4.  **For the Text Version:**
    * Set `\setbool{showphoto}{false}` (default).

## Files

* [`CV.tex`](CV.tex): LaTeX source.
* [`cv.pdf`](cv.pdf): compiled CV.

---

### ⬅️ [Return to Main Portfolio](../README.md)
