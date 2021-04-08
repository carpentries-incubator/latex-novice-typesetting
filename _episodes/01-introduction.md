---
title: "Introduction"
teaching: 0
exercises: 0
questions:
- "Key question: What is LaTeX used for?"
- "Key question: How can I create a new typeset document?"
objectives:
- "First learning objective. How to create a new LaTeX project in Overleaf."
- "Second learning objective. Become familiar with the Overleaf ecosystem."
- "Third learning objective. Learn what the minimum requirements for a LaTeX document are."
- "Fourth learning objective. Be able to identify an element's role in a LaTeX document."
keypoints:
- "First key point. Typesetting is used in many domains to convey information in a more readable format."
- "Second key point. Creating a new, minimal document requires a document declaration, a preamble, and a document body."
- "Third key point. LaTeX documents consist of commands, environments, and regular text. Commands may take arguments and/or options."
---


## What is LaTeX
LaTeX is a typesetting language, useful for combining text with mathematical equations, figures, tables, and citations, among other things.

LaTeX is written like a mark-up language, meaning that formatting (including bold text, bullet points, and changes in font size) is indicated by the use of commands, special characters, or *environments*.

In order to produce the actual document, this mark-up text must be *compiled*. Errors in the mark-up can either be non-fatal, meaning the document will compile with some warnings; or fatal, meaning the document will fail to compile.

## Our first LaTeX document
We'll start by creating a new, 'blank', file in Overleaf. You'll notice that its idea of a blank file is not actually an empty one.

Overleaf fills in a lot of things by default, which is one of the benefits to using it; it makes it very easy to get up-and-running in LaTeX.

There are three parts to the Overleaf window: the file navigator, the text editor, and the preview pane.

In the text editor for our 'blank' document, we can see all of the elements necessary to create a minimally-compilable document in LaTeX (and then some).


```latex
\documentclass{article}
\usepackage[utf8]{inputenc}

\title{Irish Fairy Tales}
\author{James Stephens}

\begin{document}

\maketitle

\section{Introduction}

\end{document}
```

Commands in LaTeX are distinguished from regular text through use of a backslash `\`. Some commands take options andor arguments. Arguments are placed inside curly braces `{}`. Options go in square brackets `[]`.

The `\begin{}` and `\end{}` commands delineate an *environment*. We'll see more about environments in later episodes; for now, I'll say that environments each have their own set of formatting rules and purpose.

### Looking at our document
If we look at the different parts of this document, starting at the top, we see:

1. the document class declaration (this document is an article)
2. the preamble
  * a package import statement (this package is used in almost everything; it specifies the unicode character set to use)
  * some metadata — this includes the title and author
3. the document body
  * the document environment `\begin{}` statement
    * the `\maketitle` command
    * a section heading  
    * the document environment `\end{}` statement

Some of these are absolutely necessary:

* the document class declaration (this document is an article)
* the document environment `begin{}` statement
* the document environment `end{}` statement

Without these, the document will not compile.

### Let's make this document a bit more interesting
Now we're going to add in some dummy text to get a sense of what a more-complete document would look like.

We'll do this using the `lipsum` package, which provides sample text blocks. We'll need to add a new `\usepackage{}` command to the document preamble and the `\lipsum` command underneath our section title.


```latex
\documentclass{article}
\usepackage[utf8]{inputenc}
\usepackage{lipsum}

\title{Irish Fairy Tales}
\author{James Stephens}

\begin{document}

\maketitle

\section{Introduction}
\lipsum

\section{Early Life}
\lipsum

\end{document}
```


> ## Challenge 1
>
> Look at the following LaTeX code and decide if it will compile as written.
> If you say no, decide why not.
>
> ```latex
> \documentclass{article}
> \usepackage[utf8]{inputenc}
>
> \title{The Playboy of the Western World}
> \author{JM Synge}
>
> \begin{document}
>
> \maketitle
>
> \section{Introduction}
>
> ```
> > ## Answer
> >
> > This code will not compile as written (or, if it does, it will throw
> > some warnings). It is missing the `\end{document}` statement.
> >
> > {: .tex}
> {: .solution}
{: .challenge}
>
>
> ## Challenge 2
>
> In the above code, which of these describes the text 'JM Synge':
>
> 1. it is a command
> 1. it is an argument
> 1. it is an option
>
> > ## Answer
> >
> > It is an argument; `\author` is a command; an option would be
> > in square brackets.
> > {: .tex}
> {: .solution}
{: .challenge}
>
> ## Challenge 3
>
> Which of these lines should not go in the document preamble?
>
> 1. `\maketitle`
> 1. `\title{R.U.R.}`
> 1. `\usepackage{graphicx}`
>
> > ## Answer
> >
> > `\maketitle` does not belong in the preamble. `\title{R.U.R.}` does,
> > because this command stores metadata about the file.
> > {: .tex}
> {: .solution}
{: .challenge}
>
> ## Challenge 4
>
> Which of these lines is optional?
>
> 1. `\begin{document}`
> 1. `\maketitle`
> 1. `\documentclass{book}`
>
> > ## Answer
> >
> > `\maketitle` is optional.
> > {: .tex}
> {: .solution}
{: .challenge}

{% include links.md %}
