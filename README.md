# Tips for greater productivity with LaTeX

This is a list of insights gleaned from a decade of using LaTeX.
LaTeX is not for most people.
You have to be able to debug the source file, and you have to be self-reliant.
You need some rudimentary programming skills and some patience.

## Why learn LaTeX?

- LaTeX is available for free. It is painless to install with a package manager.
- It has been around in its present form for 35 years, so it is likely to be around for another 35 years according to the [Lindy effect](https://wiki2.org/en/Lindy_effect).
- The tex files are plain text and easy to put under version control.
- The tex files are tiny compared to a word processing document containing the same information.
- Long tex files and the resulting PDF files are easy to scroll quickly; this is not the case for word processing documents.
- The support for math type-setting is among the best.
- The support for generating automatically tables of contents, bibliographies, indices, glossaries, and lists of figures, tables, code, and equations is very strong.
- You have exquisite and precise control over the appearance of the output, largely via a vast library of packages. It is likely that what you want to do has been done before via a library that someone else developed.
- The bulk of your prose does not require much in the way of LaTeX coding. The LaTeX markup is out of your way most of the time.
- After you configure that preamble of the tex file to generate the features that you want in a particular kind of document, your work is done. You can reuse the preamble for the next several decades with only minor modifications as packages wax and wane.
- You can also reuse LaTeX code in the form of code snippets. Snippets can enhance your productivity in ways that are still not possible in word processing documents thanks to tab triggers and mirrored tab stops.
- Word processing documents were designed for writing business letters and not much less. For everything else, LaTeX is better. LaTeX is also good for business letters. Most academics use word processors for historic reasons.

## Why not the alternatives to LaTeX

- [Markdown](https://wiki2.org/en/Markdown) (and all of its variants: even Rmarkdown and bookdown) are great for very simple documents. The rendered PDFs are beautiful. It is a great starter language for working with markup documents. However, it does not support automatic generation of indices.
- [ReStructuredTexT](https://wiki2.org/en/ReStructuredText) may be the next step-up in terms of sophistication, but it was designed to meet the needs of Python developers to document their code. It does a good job of meeting that need, but it is also quite limited as a result.
- [Asciidoc](https://wiki2.org/en/AsciiDoc) is a step closer to LaTeX. However, it imports rendered PNG files of equations that look horrible. It, too, fails to generate indices. 
- [Org-mode](https://orgmode.org/) is a very powerful markup language with added features for time and knowledge management. You can work in org-mode all day. It is a very complete work environment. However, org files are translated to LaTeX. Org recognizes most LaTeX markup. You have to learn LaTeX to get the most out of document generation with org-mode. Here are some templates for a generic [manuscript](https://github.com/MooersLab/manuscriptInOrg) and a [writing log](https://github.com/MooersLab/writingLogTemplateInOrg).
- HTML is obviously great for making web-pages. You can use it to generate documents too. Knowledge of HTML is useful when you run into the limitations of GitHub markdown.

I have experience with all of the above.
I use org-mode, markdown, and HTML everyday and ReStructuredTexT once a year.

## Start with Overleaf

[Overleaf](https://en.wikipedia.org/wiki/Overleaf) was created by two mathematicians and is run by PhDs in science.
It is based in England.


[Overleaf.com](https://www.overleaf.com/) provides free accounts.
I used a free account for about a year.
Then I wanted to do some collaborative writing, and I needed more disk space for some larger book projects that had bulky image files.
I then bought a license.

The [documentation about LaTeX](https://www.overleaf.com/learn) on the Overleaf website is excellent.
It is the first place you should go to when starting out.

Each of your writing project will be accessible from your multiple devices.
Each writing project is lists in projects page.
Each writing project as a unique URL that you can use to directly access the writing project from an index.html file or an org file.

Overleaf's built-in support for debugging is excellent.
Its support for debugging was one of the winning features for me.

Overleaf compiles your document to PDF very quickly and painlessly.
Inspect the output.aux for leads to the source of the errors when the error messages do not supply enough information.

## Use version control

Each Overleaf project has its own git repository.
You can `git clone` your Overleaf project to your local computer.
Take care not to get the two versions out of synch while writing or editing.

You can also git clone your project from Overleaf to GitHub but GitHub will charge you for this privilege.
If you have an academic account that is private, you can clone it from your computer to that account.


## Use the browser bookmark bar to fast access

The URL of the Overleaf writing project can be added to the browser toolbar for rapid access to the writing project.

## Start with simple projects

There is not that much in the way of coding to learn for writing the heart of a LaTeX document between the begin document and end document statement.
The trouble comes when you extend LaTeX with packages.

## Start with a simple manuscript format

Initially, avoid using the complex template documents for journal articles that you find on the Overleaf website.
You can submit a plain [double-spaced manuscript document](https://github.com/MooersLab/manuscriptInLaTeX) on the first submission for any journal.
Do not waste time on complex configurations for the first submission.
You may have to send the manuscript to a different journal that requires a different template.

## Write one sentence per line

This style of writing eases version control with git (Version control with git is impossible with Word documents).
This format of writing also eases the shuffling of sentences during rewriting.
Each of these two reasons alone is sufficient to use this unconventional format of writing.
You quickly adapt to reading text in this format.
This format might be easier to comprehend because each complete thought is on a separate line.

The [twautex](https://github.com/jeeger/twauctex) package in Emacs eases writing one sentence per line.
It is not in MELPA yet.
You have to install it manually.

## Global.bib: skip the synching

You can synch your global.bin file to your Overleaf writing project by storing it on Google Drive or DropBox.
I spent a lot of time on this and found that it was too complicated.
One weakness is the need for continuous synching with Dropbox or Google Drive.
I find it easier to upload to the Overleaf project a new version of the global.bib file as needed.


## Consider using JabRef to manage a global.bib file

Although versious text edtiors have packages for managing BibTeX libarary flles, I am using JabRef.
[JabRef.app](https://www.jabref.org/) is a free, open-source Java-based stand-a-lone application for managing and searching your Bibtex library file.
JabRep has tools for finding duplicate and damaged entries.
A JabRef plugin for web browsers is available.
It will send the BibTeX for an article to JabRef and download, relabel, and store in a folder of your choice the associated PDF when the current webpage is for an article on a PubMed, Arvix, or some journal website.

I have JabRef configured to relabel the PDF with the citekey.
My citekey format is `FirstAuthorLastNameYearTitle'.
The citekey has no dashes or underscores or whitespaces.
The latter are a pain to work with on Unix-like systems.
The title is in Camel case or Pascal case.
You quickly get used to reading CamelCase.

When manually adding the BibTeX info to JabRef, I click the generate-key button in JabRef to autogenerate the citekey for an entry.
I store all of the BibTeX entries in one global.bib file.
It has over 7100 entries and is automatically backed up.
Its size is not an issue in JabRef, on Overleaf, or in Emacs.

A similar automated PDF retrieval and relabeling system is available through Professor John Kitchin's [org-ref](https://github.com/jkitchin/org-ref) package for org-mode in Emacs.
This functionality is not available in Emacs for LaTeX-mode, hence my workaround solution with JabRef.

## Writing math equations

Overleaf does not support code snippets.
Emacs's [yasnippet](https://github.com/joaotavora/yasnippet) package eases creation of snippets.
Snippets and especially the [LaTeX-auto-acitvating-snippets package](https://github.com/tecosaur/LaTeX-auto-activating-snippets) can ease the writing of equations.
The Swedish mathematician Mark Olson provides an [awesome demo](https://www.youtube.com/watch?v=5cGsiRtBK9I) of these features in a short video.

Overleaf is not the best environment for writing a lot of equations.
If snippets in Emacs is too overwhelming, use the GUI-driven equation editor in [LyX](https://www.lyx.org/) or use the [LaTeXiT.app](https://www.chachatelier.fr/latexit/) to typeset the math equations and paste the assembled code into your LaTeX document.

Emacs has great support for writing in LaTeX.
For me, Vim was the penultimate editor but Emacs as the ultimate one.
There is no more advanced editor.
It is at the end of the learning editor learning spiral.

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

## How to deal with URLs that bleed into the right margin

Web addresses or URLs are frequently used to refer to resources on the World Wide Web.
URLs are useful to display because they can evolve.
Knowledge of an outdated URL can aid the discovery of the current URL.
However, LaTeX does not know how to line wrap URL so they project into the right margin.

To address this problem, I put URLs in footnotes at the bottom of the page where they are out of the way.
I use the the command `\footnote{\url{ }}`.
I have put this in a yasnippet called *furl*.

```elisp
# contributor: Blaine Mooers bmooers1@gmail.com
# key: furl
# group: urls
# name: Send a url to a footnote.
# --
\footnote{\url{${1:http}}}.
$0
```

I copy the URL of interest to the clipboard.
Then, at the end of the sentence, I enter *furl* and Control-o.
I had mapped C-o to the yasnippet command for inserting a snippet; this is equivalent to using tab with a tab trigger.

Then the code in the snippet appears.
I paste the URL on the placeholder `http` and then hit tab.
The cursor moves out of the braces and over the period to the start of the next sentence on a new line.
LaTeX automatically handles the generation of the footnote number and its placement in the footer of the page.


## Multipart documents

I can compile to PDF at a book with 1000 pages assemble from 400 individual documents, a table of contents, bibliography, and index in about a minute on Overleaf.com.
The same operation takes several minutes on my local computer.

### main.tex for books

Books are best assembled from multiple documents, with one document per chapter.
This modularization eases the shuffling of the order of the chapters and the addition of new chapters.
It is super easy to shift lines of text up and down in Emacs without using the mouse to make selections.

Multipart documents require a *main.tex* file that I store at the top level of the project directory.
I use it to source a *0AAAcontents.tex* file (which has the *input* or *include* commands for importing the individual files for each chapter and appendix) and a mybookPreamble.tex that contains my preamble for books.
This modularization of the main.tex file has greatly eased debugging.

I frequently edit the *0AAAcontents.tex* file as I add chapters and appendices.
I named this file *0AAAcontents.tex* so that it appears at the top of the list of files in a `./Contents` folder where I store the chapter files and all other input files for the book.
I store the figures, code listings, and appendices in subfolders of `./Contents` to reduce the clutter.
I start the filename of chapters with `Ch` to distinguish them from other types of files.
I do not include chapter numbers in the filenames of chapter because their absolute position shifts over time.
I use the order of listing of the include commands in the *0AAAcontents.tex* file automatically  handle the numbering of the chapters.


The path to the main.tex file has to be included on the top line of each component file on Overleaf: `%!TEX root = ../main.tex` For Chapter files and `%!TEX root =  ../../main.tex` for the appendix files that are stored in the folder `./Contents/appendices`.
The percent sign is the comment mark for LaTeX, so its presence in the first column of the first line is counter-intuitive.

Similarly, four lines of code have to be at the end of each tex file for compiling by Emacs.
The code below works with the default LaTeX mode.
Alter the code when working with Auctex in Emacs.
Some other editors like TextMate require similar metadata to find the master main.tex file.
The code at the top for the file for Overleaf and the code at the bottom of the file for Emacs can be present in the same file because they do not interfere with keep other.

```latex
%%% Local Variables: ***
%%% mode:latex ***
%%% tex-main-file: "../main.tex"  ***
%%% End: ***
```

A useful template for a book chapter follows:


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

This template is made into a yasnippet snippet for Emacs as shown below.
The $1 tab trigger is mirrored so the whatever you enter at the first site is propagate to the other sites.
This saves time.
The snippet includes in a comment some basic Emacs commands that I use when in LaTeX mode.

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
% C-c y for a hydra for yasnippets (Hydras are very cool! They save time. Learn about them.)
% Fn F1 to invoke a hdyra for magit: mc for commit and mp for push. Yes, use git inside an Emacs buffer has opened a file under git version control.


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

Magit is the Emacs package that enables running git from inside Emacs.
The magit hydra came from this emacs.stackexchange [post](https://emacs.stackexchange.com/questions/21597/using-magit-for-the-most-basic-add-commit-push).
I have pasted it below for completeness.
Hydras display a temporary menu to guide your selection of commands.
I regret not learning about them sooner.


```elisp
(defhydra yt-hydra/help (:color blue :hint nil)
  "
_mp_ magit-push #_mc_ magit-commit #_md_ magit diff #_mla_ magit diff #_mla_ magit status
"
  ;;Magit part
  ("mp" magit-push)
  ("mc" magit-commit)
  ("md" magit-diff)
  ("mla" magit-log-all)
  ("ms" magit-status)
  )
(global-set-key (kbd "<f1>") 'yt-hydra/help/body)

```

The hydra for yasnippets is below:

```elisp
;; A cool hydra for finding snippets at point. Invoke wit C-c y.
(use-package hydra
  :defer 2
  :bind ("C-c y" . hydra-yasnippet/body))

(defhydra hydra-yasnippet (:color blue)
  "
  ^
  ^YASnippet^          ^Do^
  ^─────────^──────────^──^────────
  _q_ quit             _i_ insert
  ^^                   _m_ mode
  ^^                   _n_ new
  ^^                   ^^
  "
  ("q" nil)
  ("i" yas-insert-snippet)
  ("m" yas-minor-mode)
  ("n" yas-new-snippet))
```

My current Emacs configuration file can be downloaded from [here](https://github.com/MooersLab/emacs30venturatreesitterconfig).
Older variants can be found elsewhere in my collection of GitHub repos.


## Reference all labels

Labels are anchors for hyperlinks in the compiled PDF.
They are often added to figures, tables, equations, and code listings, and then they are referred to from the text.
When reusing code, it is too easy to propagate the same label and to fail to add the reference to the label.
Each label must be unique, and each must be referenced.
It is best to think of labels and references as being inseparable pairs.
Otherwise, you will have to spend a lot of time dealing with labels that lack references during debugging.

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
Furthermore, LaTeX supports my pursuit of the [FAIR](https://www.go-fair.org/fair-principles/) principles.
I retain word processors on my computer to collaborate with colleagues who do not know LaTeX.

