LaTex Tutorial
==============

Requirements
--------------

For this tutorial you will need two things:

- LaTex; https://www.tug.org/texlive/
- An editor of your choice (such as VScode/Sublime/Notepad/PyCharm)

Creating and compiling `main.tex`
----------------------------------

Navigate to desktop (`cd Desktop`) and create a folder named latex (`mkdir
latex`) and navigate to it (`cd latex`). Now open the `latex` directory with
your editor and keep terminal window open.

In the folder `latex` let's create a file named `main.tex`. After you create
the file make sure it looks like this (& remember to save):

```latex
\documentclass{article}

\begin{document}
Hallo, world!
\end{document}
```

We now need to compile the `main.tex` document using LaTex. LaTex has several
compilers. For the purposes of this tutorial we will use the compiler `pdflatex`.
For more information on compiler see here:  https://www.overleaf.com/learn/latex/Choosing_a_LaTeX_Compiler. 

To compile run the following command in your terminal/git bash:

```shell
$ pdflatex main.tex
```

To see the `pdf` which was create run the following command:

```shell
$ open main.pdf
```

or if you are on Windows:

```shell
$ start main.pdf
```

In your document you can include comments. Comments are useful sentences to
yourself and to your collaborators. In LaTex the `%` sign is used to denote
comments. For example:

```latex
\documentclass{article} % There are various classes of documents - we will use the article class


\begin{document} % This line starts the document
Hallo, world!
\end{document}
```

The preamble
-------------

The code that precedes the `\begin{document}` statement is commonly referred to as
the 'preamble'. It typically includes instructions to set a document title, load
specific packages, and perform other necessary tasks. To set the title of your
document, you can use the following code, which should be inserted in the
preamble.

```latex
\documentclass{article} % There are various classes of documents - we will use the article class

\title{A Document}
\author{Nikoleta E. Glynatsi}
\date{\today}

\begin{document}  % This line starts the document

\maketitle

Hello, world!
\end{document}
```

Remember to compile your document and have a look at the `pdf` document
that was generated.

Including Figures
----------------

In our manuscripts we want to be able to include figures. To include a figure
we need to use the package `graphicx`. In LaTeX packages are included in the
preamble using the `usepackage` command. Include the following in the preamble:

```latex
\usepackage{graphicx}
```
The following code includes a figure:

```latex
\includegraphics{path_to_picture}
```

We can center the figure with the center environment:

```latex
\begin{center}
    \includegraphics{path_to_picture}
\end{center}
```

We can also pass options to `includegraphics` to specify the width. For example,
this ensures the picture will be 60% of the width of the page:

```latex
\begin{center}
    \includegraphics[width=.6\textwidth]{path_to_picture}
\end{center}
```

We want to be able to reference the figures of our manuscript and to
write descriptive captions. In LaTex this is done by using the concepts of
"floats". Tweak your document to look as follows:

```latex
Figure~\ref{my_picture} shows a picture.

\begin{figure}[htbp]
\begin{center}
    \includegraphics[width=.6\textwidth]{path_to_picture}
\end{center}
\caption{A picture}
\label{fig:my_picture}
\end{figure}
```

Note that these are called "floats" because they are designed to move in the
document to ensure the best use of space. LaTex will aim to place floats in an
efficient manner however some of the rules it follows can be broken by passing
the following options:

- h: try to place the float where it is indicated by the code.
- t: the float can be allowed in the top of the page.
- b: the float can be allowed in the bottom of the page.
- p: the float can be allowed on a page or column by itself.


Note that if you use the `pdflatex` command to compile the document now
the sentence `Figure~\ref{my_picture} shows a picture.` appears with
a question mark. To fix this you need to re-run the compiling command.


Including Tables
----------------

Tables are also something we want to include in our manuscript. The following
code creates a table. `c`, `r`, and `l` tags that indicate text alignment.
Note that to be able to use the commands `\toprule` etc you in to add in
pre the following line:

```latex
\usepackage{booktabs}
```

```latex
Table~\ref{table:my_table} shows a table.

\begin{table}
    \begin{center}
        \begin{tabular}{l|c|r|}
            \toprule
            Name        & Last Name & Year \\
            \midrule
            Nikoleta    & Glynatsi   & 2020\\
            Marta       & Couto & 2023\\
            \bottomrule
        \end{tabular}
    \end{center}
    \caption{A table}
    \label{table:my_table}
\end{table}
```

Compile the document again by running the `pdflatex` command twice.

LaTex matrices are vastly used. Most programming languages out there allow you
to export a table or an array to a LaTex format. So you can do this instead of
copy pasting each value at a time.

- Matlab: https://www.mathworks.com/matlabcentral/fileexchange/69063-matlab-table-to-latex-conversor
- R: https://stackoverflow.com/questions/5465314/tools-for-making-latex-tables-in-r
- Python: https://stackoverflow.com/questions/14380371/export-a-latex-table-from-pandas-dataframe

Note that you can always write the table to a file an include in the `main.tex`
using the command `\input`. For example:

```latex
\begin{table}[!hbtp]
    \begin{center}
        \input{tex/regression_results.tex}
        \caption{Regression results.}
        \label{table:regression}
    \end{center}
\end{table}
```

Bibliography
-------------

To create a bibliography we need to store the bibliographic information in a
separate 'bibtex' file. In this file you include bibliographic information for
the various references you might have. Note that the information needs
to have a specific style (`bibtex`). There are a variety of tools that will give
you bibtex code for any given reference (Google Scholar, JabRef, Zotero,
Mendeley).

For example let's assume we want to cite the paper "The hitchhiker's guide to
altruism: Gene-culture coevolution, and the internalization of norms". First
we need to create a new file `bibliography.bib` (this is where all
the bibliographic information will be included). The add in the empty
file the following:

```
@article{gintis:JTB:2003,
  title={The hitchhiker's guide to altruism: Gene-culture coevolution, and the internalization of norms},
  author={Gintis, Herbert},
  journal={Journal of theoretical biology},
  volume={220},
  number={4},
  pages={407--418},
  year={2003},
  publisher={Elsevier}
}
```
We can then reference the 'key' (for the above it is `gintis:JTB:2003`) for any
document in the bibliography file using the following:

```shell
A very helpful reference with a cool title \cite{gintis:JTB:2003}.

\bibliographystyle{plain}

\bibliography{bibliography.bib}
```

To compile the document now note that you need to run the following sequence
of commands:

```shell
pdflatex main.tex -> bibtex main -> pdflatex main.tex -> pdflatex main.tex
```

The command `\bibliographystyle{plain}` specifies the style we want to use. For
more bibliography styles check:
https://www.overleaf.com/learn/latex/Bibtex_bibliography_styles.

Latexmk
--------

So far we saw cases where we had to run the `pdflatex` command twice, or a
sequence of commands when we wanted to compile our bibliography. There is a tool
that runs latex commands as many time as necessary.
https://mg.readthedocs.io/latexmk.html Once it is installed, you can compile the
latex files by just running `latexmk main.tex`.