# refstate

The `refstate` package provides a mechanism to pre-state and re-state theorems in a LaTeX document.
It relies on the implementation details of the `amsthm` package and **may break if those details change**.

## Usage

To use the `refstate` package, install `refstate.sty` and include it in your document preamble with:

```tex
\usepackage{refstate}
```

Declare your theorem environments like normal.

```tex
\theoremstyle{plain}
\newtheorem{THM}{Theorem}[section]
```

You can then use the `store` environment to define a theorem like this.

```tex
\begin{store}{THM}[Blue sky theorem]\label{thmmain}
    The sky is blue.
\end{store}
```

Elsewhere in the document (before or after), use the `refstate` command to reference it.

```tex
\refstate{thmmain}
```

## Building

Run `tex refstate.dtx` to rebuild `refstate.sty`, then `pdflatex refstate.dtx` to compile the documentation.