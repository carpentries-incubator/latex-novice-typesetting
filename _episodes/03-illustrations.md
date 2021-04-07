---
title: "llustrations"
teaching: 0
exercises: 0
questions:
- "Key question: How can I add images to my document?"
- "Key question: How does image placement interact with the surrounding text?"
objectives:
- "First learning objective. Place an image at a fixed location."
- "Second learning objective. Learn the difference between fixed and floating images."
- "Third learning objective. See how to use options to change how inserted images appear."
keypoints:
- "First key point. Including an image requires the use of a command, and possibly a `figure` environment, an the specification of the path to the image (which may be more than just the filename, if the image is in a subdirectory)."
- "Second key point. Floats are placed by LaTeX in locations that will look nice; this is determined by a set of rules (that can be modified, if one is so inclined)."
- "Third key point. The appearance of images can be customised using options to `\\includegraphics{}`."
- "Fourth key point. Captions are short descriptions of an image. Labels are a way to refer to them within the text."
---

### Illustrations

We've now got a pretty reasonable-looking document. Let's see about adding in some images.

We're going to be using a command called `\includegraphcs[]{}`. It can take many different options, and requires one argument—the path to the image file. This command comes from the `graphicx` package, which we will also need to include

In Chapter 1, *The Banquet*, we are going to add `troubadour.jpeg`.

```latex
% in brawl_at_allen.tex
\usepackage{graphicx}

...

\chapter{The Banquet}

\includegraphics[]{troubadour}
```

When this is rendered, the image should appear, but its placement is not going to be ideal. Inserting an image in this way means that the image must appear before any of the text in Chapter 1, **no matter what; even if it makes the document look ugly.**

If we don't want this rigid behaviour, we can use a new environment, called a `float`. Floats come in two flavours: `figure`, and `table`. We will use the `figure` version.

The `figure` environment requires a `\begin{}` and `\end{}` statement, just like the `document` environment. Overleaf will autofill some of the different parts of this, as well.

The image will be automatically centred with `\centering`, and caption and label commands will also appear; these are optional, but helpful. The caption can be given a short description of the image as an argument; the label makes it possible to cross-reference the image in the text. We'll look cross-references later on. For now, you can leave the label as the default, or pick something short and descriptive.

```latex
\begin{figure}
    \centering
    \includegraphics[]{troubadour}
    \caption{A troubadour, performing}
    \label{fig:troubadour}
\end{figure}
```

Now, when the document is compiled, the figure will fit into the document more naturally.

Now let's add in a figure to Chapter 2. This time the image will be `battle.jpeg`.

```latex
% in story.tex
\begin{figure}
    \centering
    \includegraphics[]{battle}
    \caption{The battle}
    \label{fig:battle}
\end{figure}
```
When we compile this, the image is too big for the page. We need to use an option with `\includegraphics` to scale it down.

```latex
% in story.tex
\begin{figure}
    \centering
    \includegraphics[scale = .5]{battle}
    \caption{Caption}
    \label{fig:my_label}
\end{figure}
```

Finding the right scaling factor is a trial-and-error process, but the default is 1.

Finally, we can add the `trial.jpeg` image to Chapter 3. This image is very wide, so it would be nice to have it rotated, so it fits better on the page. For this, we will need to add a new package: `lscape`.


```latex
\usepackage{lipsum}
\usepackage{graphicx}
\usepackage{lscape}
```

This package gives us a new environment, called `landscape`. We need to place the entire figure environment within it.

```latex
\chapter{The Trial}

\begin{landscape} 
\begin{figure}
    \centering
    \includegraphics[]{trial}
    \caption{The trial}
    \label{fig:trial}
\end{figure}
\end{landscape}
```

It looks like we may also need to scale this image down a bit. Experiment with different sizes.

```latex
\chapter{The Trial}

\begin{landscape}
\begin{figure}
    \centering
    \includegraphics[scale = .8]{trial}
    \caption{The trial}
    \label{fig:trial}
\end{figure}
\end{landscape}
```


> ## Challenge
>
> Will this code insert an image at a fixed location, or one whose location is flexible?
>
> ```latex
> \includegraphics[scale=.7]{constellations}
> ```
>
> > ## Answer
> > This code will insert an image whose location is fixed because it is not inside a floating environment.
> > {: .tex}
> {: .solution}
{: .challenge}

>
> ## Challenge
> `\includegraphics[]{}` has many different options it can take. Apply the `angle` option to the first image we added; its value should be a whole number between 0 and 360. You can also try this with the other images; multiple options are specified as a comma-separated list.
>
> > ## Answer
> > ```latex
> > \begin{figure}
> >     \centering
> >     \includegraphics[angle=30]{troubadour}
> >     \caption{A troubadour, performing}
> >     \label{fig:troubadour}
> > \end{figure}
> > ```
> > {: .tex}
> {: .solution}
{: .challenge}
