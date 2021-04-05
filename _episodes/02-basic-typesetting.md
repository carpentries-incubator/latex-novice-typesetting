# Basic typesetting

We are now going to actually typeset some text. You'll need to upload the `brawl_at_allen.txt`, `troubadour.jpeg`, `battle.jpeg`, and `trial.jpeg` files, which you can download from [here](https://github.com/carpentries-incubator/latex-novice-typesetting/blob/gh-pages/data/).

We're going to create a new document, which we will call `story.tex`. This time, we will actually get a blank document from Overleaf (because we didn't start a new project), so we're going to have to remember the necessary parts of the document structure.

```latex
\documentclass{book}
\usepackage[utf8]{inputenc}

\author{James Stephens}
\title{Irish Fairy Tales}
\date{}

\begin{document}
\maketitle



\end{document}
```

Previously, we inserted some random text using `lipsum`, but because that is generated via a command, we couldn't format it at all. To be able to do this, we need to have access to the text prior to compiling the document. We have two options for adding text in to our new document.

1.  We can just put the text itself into the document.
```latex
\documentclass{book}
\usepackage[utf8]{inputenc}

\author{James Stephens}
\title{Irish Fairy Tales}
\date{}

\begin{document}
\maketitle

When the wind picked up the fire spread
And the grapevines seemed left for dead
And the northern sky looked like the end of days
The end of days

\end{document}
```

1. Or, we can keep the text in a separate document (like `brawl_at_allen.txt`) and use a command to insert it (similar to what we did with `lipsum`, before):

```latex
% in story.tex
\documentclass{book}
\usepackage[utf8]{inputenc}

\author{James Stephens}
\title{Irish Fairy Tales}
\date{}

\begin{document}
\maketitle

\input{brawl_at_allen.txt} % this must have the file path as its argument

\end{document}
```

Both options have pros and cons. Keeping everything in one file means fewer files to deal with, but it can reach a point where finding different parts is difficult.

Using separate files keeps any one file from becoming unwieldy, but runs the risk of having too many files to keep track of.

The right depends on how you like to work, and the project at hand. For now, we'll keep the text in its own file, but we'll change its extension to `.tex`.

### Formatting

Sometimes you might be actively writing a document and doing formatting-type things as you write. This is one way to make a $\Latex$ document. The other is to take text that is already written and simply typeset it. This is what we're going to do now.

We previously saw the `\section{}` command in our article example. Our current document is in the document class 'book', so we will be using variations on `\section{}`, called `\part{}` and `\chapter{}`. The book document class defaults to things like: printing front and back, different margins for even and odd pages, and starting every chapter on an odd page.

`The Little Brawl at Allen` has three chapters, and is one of three fairy tales to be included in this document. Let's add a part heading with the story title, some chapter headings, and a Table of Contents. (I've made up some chapter titles to go with the story.)

Chapter titles:
* The Banquet
* The Brawl
* The Trial

```latex
% in brawl_at_allen.tex
\part{The Little Brawl at Allen}

\chapter{The Banquet}

```

The `\chapter{}` command takes one argument—the chapter title. We do not need to give it a number; these are assigned automatically, in the order the compiler encounters the commands.

Now add the other two `\chapter{}` commands. (The 'find' option might be helpful here.)

Once all four commands have been added, we can add the `\tableofcontents` command in `story.tex` and the headings will automatically appear there.

```latex
% in story.tex
\begin{document}
\maketitle

\tableofcontents

```

The `\tableofcontents` command does not take any arguments.

### Illustrations

We've now got a pretty reasonable-looking document. Let's see about adding in some images.

We're going to be using a command called `\includegraphcs[]{}`. It can take many different options, and requires one argument—the path to the image file.

In Chapter 1, *The Banquet*, we are going to add `troubadour.jpeg`.

```latex
% in brawl_at_allen.tex
\chapter{The Banquet}

\includegraphics[]{troubadour}
```

When this is rendered, the image should appear, but its placement is not going to be ideal. Inserting an image in this way means that the image must appear before any of the text in Chapter 1, **no matter what; even if it makes the document look ugly.**

If we don't want this rigid behaviour, we can use a new environment, called a `float`. Floats come in two flavours: `figure`, and `table`. We will use the `figure` version.

The `figure` environment requires a `\begin{}` and `\end{}` statement, just like the `document` environment.

```latex
\begin{figure}
    \centering
    \includegraphics[]{troubadour}
    %\caption{Caption}
    %\label{fig:my_label}
\end{figure}
```

Now, when the document is compiled, the figure will fit into the document more naturally.
