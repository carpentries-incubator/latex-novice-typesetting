---
title: "Basic Formatting"
teaching: 0
exercises: 0
questions:
- "Key question: How can I create headings for different things?"
- "Key question: How can I format text into boldface, or italics?"
- "Key question: How can I add a footnote to indicate important information?"
objectives:
- "First learning objective. Be able to create headings."
- "Second learning objective. Understand how to add a Table of Contents."
- "Third learning objective. Learn that there are two different ways to create boldface and italicised text."
- "Fourth learning objective. Be able to add a footnote in the correct place."
keypoints:
- "First key point. Headings are automatically numbered in the correct order and added to the Table of Contents."
- "Second key point. `\\textbf{}` and `\\textt{}` format text given to them as an argument. `\\bfseries` and `\\itshape` format all of the text following them, or within a specified environment."
- "Third key point. A separate 'mark' can be created for chapters, sections, or other named headings that consists of a shorter version of the name for use in headers and the Table of Contents."
---

# Basic typesetting

We are now going to actually typeset some text. You'll need to upload the `brawl_at_allen.txt`, `troubadour.jpeg`, `battle.jpeg`, and `trial.jpeg` files, which you can download from [here](https://github.com/carpentries-incubator/latex-novice-typesetting/blob/gh-pages/data/).

We are first going to renamed the current `main.tex` document to `old.tex`; then, we're going to create a new document, which we will call `main.tex`. This time, we will actually get a blank document from Overleaf (because we didn't start a new project), so we're going to have to remember the necessary parts of the document structure.

We are renaming the old file because Overleaf will automatically compile `main.tex`, even if we hit compile with a different file open in the editor; otherwise, we would have to swap back and forth between files a lot.

```latex
% in main.tex
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
% in main.tex
\documentclass{book}
\usepackage[utf8]{inputenc}

\author{James Stephens}
\title{Irish Fairy Tales}
\date{}

\begin{document}
\maketitle

\input{brawl_at_allen.tex} % this must have the file path as its argument

\end{document}
```

Both options have pros and cons. Keeping everything in one file means fewer files to deal with, but it can reach a point where finding different parts is difficult.

Using separate files keeps any one file from becoming unwieldy, but runs the risk of having too many files to keep track of.

The right depends on how you like to work, and the project at hand. For now, we'll keep the text in its own file, but we'll change its extension to `.tex`.

### Formatting

Sometimes you might be actively writing a document and doing formatting-type things as you write. This is one way to make a LaTeX document. The other is to take text that is already written and simply typeset it. This is what we're going to do now.

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

Once all four commands have been added, we can add the `\tableofcontents` command in `main.tex` and the headings will automatically appear there.

```latex
% in main.tex
\begin{document}
\maketitle

\tableofcontents

```

The `\tableofcontents` command does not take any arguments.

### Bold and italicised text and footnotes

Making text bold or italicised is done using some new commands: `\textbf{}` and `\textit{}`. The text to be formatted is given as an argument to the command.

There is a note about the text found at the beginning of Chapter 2; let's place that in italics to offset it more, and but the word 'Note:' in bold.

```latex
% in brawl_at_allen.tex
\chapter{The Battle}

\textbf{Note:} \textit{This version of the death of Uail is not correct. Also Cnocha is not in Lochlann but in Ireland.}\\
```

This formatting helps differentiate the note from the rest of the text. The double slash at the end creates a linebreak, which physically separates the note from the rest of the chapter.

Another option would be to place this in a footnote. This is done with the `\footnote{}` command. The argument will be the text of the footnote. (We could leave the bold/italics, but will remove them for now.)

```latex
% in brawl_at_allen.tex
\chapter{The Battle}

\footnote{This version of the death of Uail is not correct. Also Cnocha is not in Lochlann but in Ireland.}
```

This places the text of the footnote down at the bottom of the page, but the footnote indicator is placed a bit awkwardly. We probably actually want to have it appear after the chapter title.

Placing the footnote command after the `}` does not fix the problem; we probably need to place it inside the curly braces.

```latex
% in brawl_at_allen.tex
\chapter{The Battle\footnote{This version of the death of Uail is not correct. Also Cnocha is not in Lochlann but in Ireland.}}
```

This throws an error. Because we didn't get it before, we know it must be a result of the new placement of the footnote command. LaTeX error messages can be hard to decipher, but in this instance the error is caused because chapter headings are not like regular text. Their appearance at the beginning of a chapter, in the Table of Contents, and in page headers is all formatted very specifically and including a footnote in the argument to the `\chapter{}` command messes some of that up.

In order to resolve this, we can add an option to the `\chapter{}` command that specifies an alternate version of the title, without the footnote.

```latex
% in brawl_at_allen.tex
\chapter[The Battle]{The Battle\footnote{This version of the death of Uail is not correct. Also Cnocha is not in Lochlann but in Ireland.}}
  ```

This option creates what is called a *chaptermark* for *The Battle* that doesn't include the footnote. Chapter- and sectionmarks are used in the Table of Contents and in page headers. While we are using it to accommodate a footnote, they can also be used to provide shortened versions of long titles.


> ##  Exercise 1
>
> Decide which of these are valid ways to input text into a document:
>
> 1.
> ```latex
> \section{Lyrics}
> When the wind picked up the fire spread
> And the grapevines seemed left for dead
> And the northern sky looked like the end of days
> The end of days
> ```
>
> 1.
> ```latex
> \section{Lyrics}
> \input{grapevine_fires.tex}
> ```
>
> 1.
> ```latex
> \section{Lyrics}
> \insert{grapevine_fires.tex}
> ```
>
> 1.
> ```latex
> \section{Lyrics}
> \include{grapevine_fires.tex}
> ```
>
> > ## Answer
> >
> > All of these are valid, except for `\insert{grapevine_fires.tex}`.
> >
> > The first option just places the text where it is typed.
> >
> > The second, is what we have used above to insert `brawl_at_allen.tex` into our document.
> >
> > We have not encountered `\include{}` in this lesson, but it is valid, so it's a bit of a trick option. Functionally, `\include{}` works similarly to `\input{}`, although it creates additional pagebreaks.
> > {: .tex}
> {: .solution}
{: .challenge}
>
>
> ## Challenge
> 1. `\textbf{}` and `\textit{}` are *commands* that change the style of text. There is another way to tell $\LaTeX$ that text should be bold or italicised; this is with the `\bfseries` and `\itshape` *declarations*. Declarations do not take an argument, instead, they modify all of the text that follows them, or is within their *environment*.
>
> Try inserting one of these declarations just after the `\begin{document}` line and observe what happens.
>
> Once you have, place the declaration inside of curly braces, as if it were the argument for a command, and adding some text after it:
>
> ```latex
> {\itshape  War with the Newts}
> ```
>
> Now, the declaration only affects the text inside the curly braces.
>
>
> ## Challenge
> 1. Use the `\itshape` and `\bfseries` declarations to typeset the note at the beginning of Chapter 2; (you can leave the footnote we created as it is and just make this new version appear below the chapter title).
>
> > ## Answer
> > ```latex
> > % in brawl_at_allen.tex
> > {\bfseries Note}{\itshape This version of the death of Uail is not correct. Also Cnocha is not in Lochlann but in Ireland.}
> > ```
> > {: .tex}
> {: .solution}
{: .challenge}
