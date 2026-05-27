# HOP-PAAL: A Formal Frogger Journey

Formal modelling and verification of a simplified version of the classic arcade
game **Frogger**, developed with **UPPAAL** for the *Formal Methods for Software
Engineering* course (Politecnico di Milano, A.Y. 2025–2026).

**Authors:** Daniele Crippa, Dario Cambi, Giorgio Ciraci.

---

## Repository structure

```
.
├── Hop-pal project - Stochastic Version.xml   # Stochastic Model
├── Hop-pal project - Symbolic Version.xml     # Stochastic Model
├── presentation/                              # LaTeX report
│   ├── presentation.tex
│   └── images/
├── .gitignore
└── README.md
```

---

## 1. Running the model in UPPAAL

### Install UPPAAL

1. Download UPPAAL from the official website: <https://uppaal.org/downloads/>
2. UPPAAL requires a **Java Runtime Environment** to run. If it does not start,
   install a recent JRE (for example from <https://adoptium.net/>).
3. Extract the downloaded archive. UPPAAL does **not** require installation: it
   runs directly from the extracted folder. Launch the executable for your
   operating system:
   - **Windows:** `uppaal.exe`
   - **macOS / Linux:** `uppaal` (or run the bundled launcher script)

### Load the project

1. Clone or download this repository.
2. Open UPPAAL.
3. Go to **File → Open System...**
4. Select the file `Hop-pal project - Symbolic Version.xml` or `Hop-pal project - Stochastic Version.xml` from the repository.

Once loaded, the templates appear under the **Editor** tab. Use the
**Simulator** tab to explore the system step by step, or the **Verifier** tab
to run the formal queries.

### Verify the properties

The queries are already included in the model. In the **Verifier** tab, select a
query and press **Check** to verify it. To obtain a counterexample or witness
trace when a property is checked, enable diagnostic traces under
**Options → Diagnostic Trace → Shortest**; the trace can then be inspected in
the **Simulator** tab.

---

## 2. Getting the report

The report is written in LaTeX and must be compiled from source.

### Requirements

- A LaTeX distribution installed and available in your system PATH:
  - **Windows:** [MiKTeX](https://miktex.org/) or TeX Live
  - **macOS:** [MacTeX](https://www.tug.org/mactex/)
  - **Linux:** TeX Live (`sudo apt install texlive-full` on Debian/Ubuntu)

### Compile from the command line

```bash
cd presentation
latexmk -pdf presentation.tex
```

This produces `presentation.pdf` in the `presentation/` folder. To clean up the
auxiliary files generated during compilation, run `latexmk -c`.

### Compile from VS Code

Alternatively, open the `presentation/` folder in **VS Code** with the
[LaTeX Workshop](https://marketplace.visualstudio.com/items?itemName=James-Yu.latex-workshop)
extension installed. Open `presentation.tex` and build the project
(`Cmd/Ctrl + Alt + B`); the PDF preview opens with `Cmd/Ctrl + Alt + V`.
