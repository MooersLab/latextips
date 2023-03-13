# Tips for greater productivity with LaTeX

This is a list of insights gleaned from a decade of using LaTeX. 
LaTeX is not for most people.
You have to be able to debug the source file, and you have to be self-reliant.
You need some rudimentary programming skills and some patience.

## Why LaTeX?

- The tex files are plain text and easy to put under version control.
- Large tex and the resulting PDF files are easy to scroll quickly.
- The support for math type-setting is excellent.
- The support for generating bibliographies, indices, and list is very strong.


## Start with Overleaf 

[Overleaf.com](https://www.overleaf.com/) provides free accounts. 
You only need the professional account if you are doing collaborative writing. 

The [documentation about LaTeX](https://www.overleaf.com/learn) on the Overleaf website is excellent. 
It is the first place you should go to when starting out.

Your writing project will be accessible from your multiple devices. 

Overleaf's built-in support for debugging is excellent. 
Overleaf compiles your document to PDF very quickly and painlessly. 
Inspect the output.aux for leads to the source of the errors when the error messages do not supply enough information.

## Use version control 

Each Overleaf project has its own git repository. 
You can `git clone` your Overleaf project to your local computer. 
Take care not to get the two versions out of synch while writing or editing.

## Use bookmark bar 

The URL of the Overleaf writing project can be added to the browser toolbar for rapid access.

## Start with simple projects

There is not that much in the way of coding to learn for writing the heart of a LaTeX document between the begin document and end document statement. 
The trouble comes when you extend LaTeX with packages.

## Start with a simple manuscript format

Avoid the complex template documents for journal articles that you can find on the Overleaf website.
You can submit a plain [double-spaced manuscript document](https://github.com/MooersLab/manuscriptInLaTeX) on the first submission for any journal. 
Do not waste time on complex configurations for the first submission. 
You may have to send the manuscript to a different journal.

## Write one sentence per line

This style of writing eases version control with git (Version control with git is impossible with Word documents). 
This format of writing also eases the shuffling of sentences during rewriting. 
Each of these reasons alone is sufficient to use it. 
You quickly learn to adapt to reading text in this format.
It might be easier to comprehend because each complete thought is on a separate line.

The [twautex](https://github.com/jeeger/twauctex) package in Emacs eases writing one sentence per line. 
It is on GitHub.

## Use JabRef to manage a global.bib file

[JabRef.app](https://www.jabref.org/) is a free, open-source Java-based stand-a-lone application for managing and searching your Bibtex library file. 
JabRep has tools for finding duplicate and damaged entries. 
A JabRef plugin for web browsers is available.
It will send the BibTeX for an article to JabRef and download, relabel, and store in a folder of your choice the associated PDF when the current webpage is for an article on a PubMed, Arvix, or some journal website.

I have JabRef configured to relabel the PDF with the citekey. 
My citekey is `FirstAuthorLastNameYearTitle'. 
The citekey has no dashes or underscores or whitespaces. 
The title is in Camel case.  
You quickly get used to reading CamelCase. 

When manually adding the BibTeX info to JabRef, I click the generate-key button in JabRef to autogenerate the citekey for an entry. 
I store all of the BibTeX entries in one global.bib file. 
It has 7100 entries and is automatically backed up.

A similar automated PDF retrieval and relabeling system is available through John Kitchin's org-ref package for org-mode. 
This functionality is not available in Emacs for LaTeX-mode, hence my workaround solution with JabRef.

## Writing math equations

Overleaf does not support code snippets. 
Emacs's [yasnippet](https://github.com/joaotavora/yasnippet) package supports eases creation of snippets. 
Emacs has great support for writing in LaTeX. 
Snippets and especially the [LaTeX-auto-acitvating-snippets package](https://github.com/tecosaur/LaTeX-auto-activating-snippets) can ease the writing of equations. 
The Swedish mathematician Mark Olson provides an [awesome demo](https://www.youtube.com/watch?v=5cGsiRtBK9I) of these features in a short video.

Overleaf is not the best environment for writing a lot of equations. 
If snippets in Emacs is too overwhelming, use the GUI-driven equation editor in [LyX](https://www.lyx.org/) or use the [LaTeXiT.app](https://www.chachatelier.fr/latexit/) to typeset the math equations and paste the assembled code into your LaTeX document.

## Know your math enivornments

One of the motivations for the development of TeX (which evolved into LaTeX) was to provided better support for typesetting math equations.
There are a large number of [equation environments](https://en.wikibooks.org/wiki/LaTeX/Advanced_Mathematics#Other_environments).
You should study them from time to time.
The LaTeX Wikibook is a good [resource](https://en.wikibooks.org/wiki/LaTeX).
Eventually, you should read these two books when time permits.

```latex
@Book{Gratzer2013MathIntoLaTeXASimpleGuideToTypesettingMathUsingAMSLaTeX,
	title = {Math into LaTeX: A Simple Guide to Typesetting Math Using AMS-LaTeX},
	publisher = {Springer Science \& Business Media},
	year = {2013},
	author = {Gr{\"a}tzer, George}
}

@Book{Graetzer2016MoreMathIntoLaTeXFifthEd,
	author = {Gr{\"a}tzer, George},
	publisher = {Springer},
	title = {More math into \LaTeX},
	year = {2016},
	edition = {Fifth Edition},
	booktitle = {More Math Into \LaTeX}
}
```


## Multipart documents

I can compile to PDF at 370 part book with 1000 pages, a table of contents, bibliography, and index in about a minute on overleaf and several minutes on my local computer.

## main.tex for books

Books are best assembled from multiple documents, with one document per chapter.
This modularization eases the shuffling of the order of the chapters.

Multipart documents require a *main.tex* file. 
I use it to source a 0AAAcontents.tex file (which has the input or include commands for importing the individual files for each chapter and appendix) and a mybookPreamble.tex that contains my preamble for books. 
This modularization of the main.tex file greatly eased debugging.

The path to the main.tex file has to be included on the top line of each component file on Overleaf: `%!TEX root = ../main.tex`. 
The percent sign is the comment mark for LaTeX so its presence in the first column of the first line is counterintuitive.

Similarly, four lines of code have to be at the end of each tex file for compiling by Emacs.
The code below works with the default LaTeX mode. 
Alter the code when working with Auctex in Emacs.
Some other editors like TextMate require similar metadata to find the master main.tex file.

```latex
%%% Local Variables: ***
%%% mode:latex ***
%%% tex-main-file: "../main.tex"  ***
%%% End: ***
```

A useful template for a book chapter would be as follows:


```latex
%!TEX root = ../main.tex

\chapter{XXXX}
\chaptermark{XXXX}
\index{XXXX!YYY}

\section{Introduction}


\section{Topic 1}
\index{Topic 1}



\section{Summary}


%%% Local Variables: ***
%%% mode:latex ***
%%% tex-main-file: "../main.tex"  ***
%%% End: ***
```

This template could be made into a yasnippet snippet in Emacs as follows.
It includes in a comment a reminder of some basic Emacs commands.

```latex
# -*- mode: snippet -*-
# name: A generic chapter
# contributor: Blaine Mooers bmooers1@gmail.com
# group: Template document
# key: ch
# --
%!TEX root = ../main.tex

\chapter{${1:LBSF report}}
\chaptermark{$1}
\index{$1}

% Emacs shortcuts in tex-mode
% C-c c-a to render as PDF and open in Skim.app (does not work with atomic-chrome)
% C-c w to display the word count (does not work with atomic-chrome)
% C-c C-w to write out to different filename
% C-x C-s to save.
% C-1 to close current buffer.
% C-c y i to open a pop-up menu for selecting a snippet.


\section*{Introduction}
$2

\section{Topic 1}
\index{Topic 1}
$3


\section{Summary}


%%% Local Variables: ***
%%% mode:latex ***
%%% tex-main-file: "../main.tex"  ***
%%% End: ***

```



## Reference all labels

Labels are anchors for hyperlinks in the compiled PDF.
They are often added to figures, tables, equations, and code listings and then they are referred to from the text.
When reusing code, it is too easy to propagate the same label. 
Each label must be unique, and each must be referenced.

## Add index keys as you write

The index entries are hyperlinked to the index keys in the final PDF.
It is all too easy to forget to add index keys.
However, they ease finding information in the document.
It is best to add the index keys as you assemble the document so that you can use them as you work on the project.
The keys serve as anchors to hyperlinks to them in the index.

The search function is Acrobat Reader can lead too many hits and is poor substitute for using index keys.


## Use keybindings

Overleaf has standard CUA, Vim, and Emacs keybindings available. 
You set the keybinding via the menu in the upper lefthand corner of the Overleaf webpage.
The keybindings can be selected on a per project basis. 

## Image format

Use PNG files or PDFs for image files. 
One drawback to Overleaf is that you cannot use postscript, EPS, or TIFF files. 
You can take a snapshot of images in these formats and save them as PNG files for uploading on Overleaf.
You can use PDFs, but you will not get a preview of the image file in Overleaf, unlike the case with PNG files. 
You have to wait for the document to be compiled by Overleaf to see an included image from a PDF.

## Indices

LaTeX will autogenerate the table of contents, indices, bibliographies, glossaries, acronym lists, lists of figures, lists of tables, list of computer code listings, and lists of equations. 
The last four lists require the use of captions that appear in the lists. 
Captions require the use of a subset of environments that are known as floats. 
I defined a *code* environment that encloses the minted environment for code listings and an *eqc* environment that does likewise for equations.
These are custom float environments that allow the use of captions. 

There may be computer RAM limits that block the generation of all of these indices. 
You may have to drop several of them.

## Epigraphs

The epigraph package supports the insertion of epigraphs below the chapter title in a book.
I store quotes in a master epigraphs.tex file in one project. 
I copy this file to other projects.

It takes a lot of time to gather quotes.
I gather quotes over the years and call upon them when needed. 
LaTeX automatically handles the formatting.

## Tables

Tables are a great strength of org-mode because they are trivial to assemble, and they even can do by row and by column computations like a spreadsheet.
In contrast, tables can be a pain to assemble in Emacs, unless you use a snippet for a table with a fixed number of rows and columns.

You can spend a lot of time configuring tables. 
There are web-tools that ease generating a template for a table. 
Beware that the publisher may not support fancy tables, so it is best to keep the format of the table as simple as possible.

## Beamer package

The beamer package is used to assemble slideshows via LaTeX. 
You can print notes with the slides for handouts. 
It is easy to recycle a beamer slideshow when making a new one. 
Code listings in beamer were tricky to code, but once you figure it out, you can use the beamer slide as a template.

You can add a section key above each frame environment in the beamer file.
These will not interfere with the compiling of the beamer file, but they do appear as an outline in the lower left in Overleaf.
This outline is useful during the assembly of the slideshow.

Slides for five of my six courses and all of my platform talks are in LaTeX. 
I hide the icons that typify a beamer slideshow. 
Most people think that I assembled my slides in PowerPoint.

You can also assemble a poster in LaTeX by using one giant beamer slide. 

## Conclusions

LaTeX meets all of my writing needs.
I retain MS Word to collaborate when MS Word only collaborators.
Furthermore, LaTeX supports my pursuit of the FAIR principles. 

