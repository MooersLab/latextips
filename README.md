# Tips for greater productivity with LaTeX

This is a list of insights gleaned from a decade of using LaTeX. 
LaTeX is not for most people.
You have to be able to debug the source file, and you have to be self-reliant.
You need some rudimentary programming skills and some patience.

## Start with Overleaf 

[Overleaf.com](https://www.overleaf.com/) provides free accounts. 
You only need the professional account if you are doing collaborative writing. 

The documentation about LaTeX on the Overleaf website is excellent. 
It is the first place you should go to when starting out.

Your writing project will be accessible from your multiple devices. 

Overleaf's built-in support for debugging is excellent. 
Overleaf compiles your document to PDF very quickly and painlessly. 
Inspect the output.aux for leads to the source of the errors when the error messages do not supply enough information.

## Use version control 

Each Overleaf project has its own git repository. You can git clone your project to your local computer. Take care not to get the two versions out of synch while writing or editing.

## Use bookmark bar 

The URL of the Overleaf writing project can be added to the browser toolbar for rapid access.

## Start with simple projects

There is not that much in the way of coding to learn for writing the heart of a LaTeX document between the begin document and end document statement. The trouble comes when you extend LaTeX with packages.

## Start with a simple manuscript format

Avoid the complex template documents for journal articles that you can find on the Overleaf website.
You can submit a plain double-spaced manuscript document on the first submission for any journal. 
Do not waste time on complex configurations for the first submission. 
You may have to send the manuscript to a different journal.

## Write one sentence per line

This style of writing eases version control with git (Version control with git is impossible with Word documents). 
This format of writing also eases the shuffling of sentences during rewriting. 
Each of these reasons alone is sufficient to use it. 
You quickly learn to adapt to reading text in this format.
It might be easier to comprehend because each complete thought is on a separate line.

The *twautex* package in Emacs eases writing one sentence per line. 
It is on GitHub.

## Use JabRef to manage a global.bib file

JabRef.app is a free, open-source Java-based stand-a-lone application for managing and searching your Bibtex library file. 
JabRep has tools for finding duplicate and damaged entries. 
A JabRef plugin for web browsers is available.
It will send the bibtex for an article to JabRef and download, relabel, and store in a folder of your choice the associated PDF when the current webpage is for an article on a PubMed, Arvix, or some journal website.

I have JabRef configured to relabel the PDF with the citekey. 
My citekey is `FirstAuthorLastNameYearTitle'. 
The citekey has no dashes or underscores or whitespaces. 
The title is in Camel case.  
You quickly get used to reading CamelCase. 

When manually adding the BibTeX info to JabRef, I click the generate-key button in JabRef to autogenerate the citekey for an entry. 
I store all of the bibtex entries in one global.bib file. 
It has 7100 entries and is automatically backed up. 
A similar automated PDF retrieval and relabeling system is available through John Kitchin's org-ref package for org-mode. 
This functionality is not available in Emacs for LaTeX-mode, hence my workaround solution with JabRef.

## Use Emacs for writing math equations

Overleaf does not support code snippets. 
Emacs's yasnippet package supports eases creation of snippets. 
Emacs has great support for writing in LaTeX. 
Snippets and especially the auto-snippet package can ease the writing of equations. 

Overleaf is not the best environment for writing a lot of equations. 
If Emacs is overwhelming, use the GUI-driven equation editor in LyX or use the LaTeXiT.app to typeset the math equations.

## Multipart documents

I can compile to PDF at 370 part book with 1000 pages, a table of contents, bibliography, and index in about a minute on overleaf and several minutes on my local computer.

## main.tex

Multipart documents require a main.tex file. 
I use it to source a 0AAAcontents.tex file (which has the input or include commands for importing the individual files for each chapter and appendix) and a mybookPreamble.tex that contains my preamble for books. 
This modularization of the main.tex file greatly eased debugging.

The path to the main.tex file has to be included on the top line of each component file on Overleaf: `%!TEX root = ../main.tex`. 
The percent sign is the comment mark for LaTeX so its presence in the first column of the first line is counterintuitive.
Similarly, four lines of code have to be at the end of each tex file for compiling by Emacs.
The code below works with the default LaTeX mode. 
Alter the code when working with Auctex.

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

This template could be made into a yasnippet snippet in Emacs.



## Reference all labels

When reusing code, it is too easy to propagate the same label. 
Each label must be unique, and each must be referenced.

## Add index keys as you write

It is all too easy to forget to add index keys.
However, they ease finding information in the document as you assemble it.
The search function is Acrobat Reader can lead too many hits and is poor substitute for using index keys.


## Use keybindings

Overleaf has standard CUA, Vim, and Emacs keybindings available. 
You select via the menau in the upper left one set to use on a per project basis. 
Select one set and master them.

## Image format

Use PNG files or PDFs. 
One drawback to Overleaf is that you cannot use postscript, EPS, or TIFF files. 
You can use PDFs, but you will not get a preview of the image file, unlike the case with PNG files. 
You have to wait for the document to be compiled by Overleaf to see an included image from a PDF.

## Indices

LaTeX will autogenerate the table of contents, indices, bibliographies, glossaries, acronym lists, lists of figures, lists of tables, list of computer code listings, and lists of equations. 
The last four lists require the use of captions that appear in the lists. 
Captions require the use of a subset of environments that are known as floats. 
I defined a code environment that encloses the minted environment for code listings and an eqc environment that does likewise for equations.
These are custom float environments that allow the use of captions. 

There may be computer RAM limits that block the generation of all of these indices. 
You may have to drop several of them.
The 

## Epigraphs

The epigraph package supports the insertion of epigraphs, which I store in a epigraphs.tex file. 
I gather quotes over the years and call upon them when needed. 
LaTeX automatically handles the formatting.

## Tables

Tables are a great strength of org-mode because they are trivial to assemble and they do computations.
In contrast, tables can be a pain to assemble in Emacs unless you use a snippet for table.

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
