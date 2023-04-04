# Thesis Template for University of Massachusetts, Lowell

This package provides a template for the University of Massachusetts, Lowell dissertation format.
Please submit pull requests to the [GitHub Repository](https://github.com/sunipkm/umlthesis) for
suggested changes/updates.

## Recommended Setup
- It is recommended to use [Visual Studio Code](https://code.visualstudio.com/) as the LaTeX editor
for this template. 
- It is further recommended that the full version of LaTeX is installed through
[TeX Live](https://www.tug.org/texlive/). An ISO image for the installer can be downloaded from TeX Live
[here](https://tug.org/texlive/acquire-iso.html). During installation of TeX Live, ensure the binaries (such as `pdflatex`, `xelatex` etc) are in `path`. You may need to grant the installer administrator privileges to change the necessary `path` settings.
- It is recommended that you fork the current repository in [GitHub](https://github.com). The repository is set up as a template and this fork will not be related to the template repository in any way. You can use the fork as a new repository that happens to come with pre-set files.
- Once the forked repository is cloned on the local file system and opened in VS Code, it will ask you to install the recommended extensions for the workspace. The extensions are listed in `.vscode/extensions.json`, and are as follows:
    - [LaTeX Workshop](https://marketplace.visualstudio.com/items?itemName=James-Yu.latex-workshop): Provides LaTeX compilation and preview support.
    - [LTex - LanguageTool grammar/spell checking](https://marketplace.visualstudio.com/items?itemName=valentjn.vscode-ltex): Provides spell checking and grammar.
- The workspace is also pre-configured with (see `.vscode/settings.json` for more):
    - Necessary recipes to compile the document.
    - Dark mode for PDF display.
    - Autosave has been disabled completely.
    - Inline suggestions and math display have been enabled.

## LaTeX Configuration

The package is divided into separate files. You can modify the file 
names and the basic contents (such as headers) in the files themselves. 
The style is mainly dictated by the file `main.tex`, but each chapter 
files also include style information for the chapter headers etc.

In Visual Studio Code, open `main.tex`. If [LaTeX Workshop](https://marketplace.visualstudio.com/items?itemName=James-Yu.latex-workshop) has been installed correctly, the `TEX` extension will be activated. The document can be compiled using the ⏵ symbol. The compiled PDF can be viewed as well.

LaTeX specific settings, imports and primary layout are defined in `main.tex`. Additionally, this file defines macros such as
- `\thesistitle`: Title of the dissertation.
- `\thesisauthor`: Author of the dissertation.
- `\thesisyear`: Year of the dissertation.
- `\thesissup`: Name of dissertation supervisor.
- `\thesisdept`: Department of candidate.
- `\thesisdegree`: Degree to be obtained by the candidate.
- `\thesisdegreeprogram` (optional): Degree program of the candidate.

The values of these macros must be updated as required.

By default, figures and tables are numbered as `chapter.figure` and `chapter.table`. i.e. Figure 2.3 implies figure 3 of chapter 2. These settings can be removed by commenting out the relevant `\renewcommand` lines in `main.tex`.

By default, chapter numbering depth is 5 (`\setcounter{secnumdepth}{5}`).

Hyperlink formatting is set to colors instead of bounding boxes by default through `\hypersetup` in `main.tex`.

## File Organization

The recommended organization is as follows, in order:
1. Cover page (`coverpage.tex`): Page 1, not numbered. Should not require any edits.
1. Copyright page (`copyright.tex`): Page 2, not numbered. Contains copyright information. Should not require any edits.
1. Signature page (`sigpage.tex`): Page 3, not numbered. Contains form for candidate and committee members' signatures. Should not require any edits, apart from uncommenting lines to add additional committee members.
1. Abstract title page (`abstitle.tex`): Page 4, numbered Roman numeral `i`, not visible. Should not require any edits.
1. Abstract page (`abs.tex`): Page 5+, numbered Roman numeral `ii` onwards, visible, contains the abstract. Must be edited.
1. Acknowledgements (`ack.tex`): Optional.
1. Table of contents (`toc.tex`): Should not require any edits.
1. List of tables (`lot.tex`): Should not require any edits.
1. List of figures (`lof.tex`): Should not require any edits.
1. Introduction (`intro.tex`): Introduction chapter.
1. Methodology (`method.tex`): Methodology chapter.
1. Results (`results.tex`): Results chapter.
1. Discussions (`disc.tex`): Discussions chapter.
1. Conclusions (`conc.tex`): Conclusions chapter.
1. References (`ref.tex`): Bibliography chapter. Should not require any edits.

Additional chapters (which are LaTeX `\section`s,) should be added as new files. Each new chapter file should start as follows:
```latex
\cleardoublepage
\vspace*{0.5in}
\begin{center}
\section{Chapter Name}
\label{sec:chapter_name}
\end{center}
\doublespacing
```
A subchapter can be added using `\subsection`s. Using `\subsection`, a maximum chapter depth of 2 can be reached. e.g., 2.3.4 implies chapter 2, section 3, subsection 4. Use `\myparagraph` to reach chapter depth of 3, e.g. 2.3.4.5.

## Notes

To get secondary captions for figures and tables to be included in the list of figures and tables, use the following `\caption` syntax:
```latex
\caption[Short caption.]{\label{label} Long caption.}
```

The bibliography goes in the file `bibfile.bib`. 

## Gitignore
By default, everything is ignored. Directories and files in subdirectories can be added selectively, see `.gitignore` for instructions.
