![Version](https://img.shields.io/static/v1?label=latextips&message=0.2&color=brightcolor)
[![License: MIT](https://img.shields.io/badge/License-MIT-blue.svg)](https://opensource.org/licenses/MIT)


# Tips for greater productivity with LaTeX

This is a list of insights gleaned from a decade of using LaTeX.
LaTeX is only for people who are patient, self-reliant, and willing to debug their tex file.


## Why learn LaTeX?

- LaTeX is available for free. It is painless to install with a package manager.
- It has been around in its present form for about 35 years, so it will likely be around for another 35 years according to the [Lindy effect](https://wiki2.org/en/Lindy_effect).
- The tex files are plain text and easily put under version control.
- The tex files are tiny compared to a word processing document containing the same information.
- Long tex files and the resulting PDF files are easy to scroll quickly; this is not the case for word processing documents.
- The support for math type-setting is among the best.
- The support for automatically generating tables of contents, bibliographies, indices, glossaries, and lists of figures, tables, code, and equations is robust.
- You have exquisite and precise control over the output's appearance, largely through a vast library of packages. What you want to do has likely been done before, using a library that someone else developed.
- The LaTeX markup is out of your way most of the time.
- After you configure that preamble of the tex file to generate the features you want in a particular document, your work is done. You can reuse the preamble for the next several decades with only minor modifications as packages wax and wane.
- You can also reuse LaTeX code in the form of code snippets. Thanks to tab triggers and mirrored tab stops, snippets can enhance your productivity in ways that are still impossible in word-processing documents.


## Why not the alternatives to LaTeX

- [Plain text](https://wiki2.org/en/Plain_text) Why not? It's simple. It is the place to start when breaking free from the grip of word processors.
- [Markdown](https://wiki2.org/en/Markdown) (and all of its variants: even R Markdown and [bookdown](https://bookdown.org/)) are great for simple documents. The rendered PDFs are beautiful. It is a great starter language for working with markup documents. However, it does not support the automatic generation of indices.
- [ReStructuredTexT](https://wiki2.org/en/ReStructuredText) may be the next step up in sophistication, but it was designed to help Python developers document their code. It does a good job of meeting that need, but it is also quite limited.
- [Asciidoc](https://wiki2.org/en/AsciiDoc) is a step closer to LaTeX. However, it imports rendered PNG files of equations that look less sharp after inclusion in PDFs. It, too, fails to generate indices. If you export the document to [DocBook](https://docbook.org/), which uses XML, you can create an index.
- [Org-mode](https://orgmode.org/) is a compelling markup language with added features for time and knowledge management. You can work in org mode all day. It is a very complete work environment. However, org files are translated to LaTeX upon export to PDF. Org recognizes most LaTeX markup. You must still learn some LaTeX to get the most out of document generation with org-mode. Here are some templates for a [generic manuscript](https://github.com/MooersLab/manuscriptInOrg) and a [writing log](https://github.com/MooersLab/writingLogTemplateInOrg) to keep track of your progress and plans for your writing project.
- HTML is great for making web pages and generating documents. Knowing HTML is useful when you encounter the limitations of GitHub Markdown.

I have experience with all of the above.
I edit org-mode, markdown, plain text, and HTML almost daily and ReStructuredTexT once a year.

## Start with Overleaf

[Overleaf](https://en.wikipedia.org/wiki/Overleaf) was created by two mathematicians and is run by PhDs in science.
It is based in England.


[Overleaf.com](https://www.overleaf.com/) provides free accounts.
I used a free account for about a year.
Then I wanted to do collaborative writing and needed more disk space for larger book projects with bulky image files.
I then bought a license.

The [documentation about LaTeX](https://www.overleaf.com/learn) on the Overleaf website is excellent.
It is the first place you should go to when starting out.

Each of your writing projects will be accessible from your multiple devices.
Each writing project is listed on the landing page for your account.
Each writing project has a unique URL that you can use to directly access the writing project from a browser bookmark, an index.html file, inside an IThoughtsX mindmap, or in an org file.

Overleaf's built-in support for debugging is exquisite.
Its support for debugging was one of the winning features for me.

Overleaf compiles your document to PDF very quickly and painlessly.
Occasionally, the error messages need to supply more information.
In this situation, inspect the output.aux for leads to the source of the errors 

## Use version control

Each Overleaf project has its own git repository.
You can `git clone` your Overleaf project to your local computer.
Do not get the two versions out of synch while writing or editing.

You can also `git clone` your project from Overleaf to GitHub, but GitHub will charge you for this privilege.
If you have a private academic account, you can clone it from your computer to that account.


## Use the browser bookmark bar to fast access

The URL of the Overleaf writing project can be added to the browser toolbar for rapid access to the writing project.

## Start with simple projects

There is not much in the way of coding to learn for writing the heart of a LaTeX document between the `\begin{document}` and `\end{document}` tags.
The trouble comes when you extend LaTeX by importing packages via the document's preamble.

## Start with a simple manuscript format

Initially, avoid using the complex template documents for journal articles on Overleaf or the publisher's websites.
You can submit a plain [double-spaced manuscript document](https://github.com/MooersLab/manuscriptInLaTeX) on the first submission for any journal.
You can save time on complex configurations for the first submission.
You may have to send the manuscript to a different journal that requires a different template.
It took me way too long to figure out this time-saving approach.

## Write one sentence per line

This writing style eases version control with git (Version control with git is impossible with Word documents).
This format of writing also eases the shuffling of sentences during rewriting.
These two reasons alone are sufficient to use this unconventional writing format.
You quickly adapt to reading text in this format.
This format might be easier to comprehend because each complete thought is on a separate line.

The [twautex](https://github.com/jeeger/twauctex) package in Emacs eases writing one sentence per line.
It is not in MELPA yet.
You have to install it manually.

## Global.bib: skip the synching

You can synch your global.bin file to your Overleaf writing project by storing it on Google Drive or DropBox.
I spent a lot of time on this and found it to be too complicated for my workflow.
One weakness is the need for continuous synching with Dropbox or Google Drive.
I find it easier to upload a new version of the global.bib file to the Overleaf project as needed.


## Consider using JabRef to manage a global.bib file

Although various text editors have packages for managing BibTeX library files, I am using JabRef.
[JabRef.app](https://www.jabref.org/) is a free, open-source Java-based stand-alone application for managing and searching your BibTeX library file.
JabRep has tools for finding duplicate and damaged entries.
A JabRef plugin for web browsers is available.
It will send the BibTeX for an article to JabRef and download, relabel, and store the associated PDF in a folder of your choice when the current webpage is for an article on PubMed, Arvix, or a journal website.

I have JabRef configured to relabel the PDF with the citekey.
My citekey format is `FirstAuthorLastNameYearTitle'.
The citekey has no dashes, underscores, or whitespaces.
The latter is a pain to work with on Unix-like systems.
The title is in Camel case or Pascal case.
You quickly get used to reading CamelCase.

When manually adding the BibTeX info to JabRef, I click the generate-key button in JabRef to autogenerate the citekey for an entry.
I store all the BibTeX entries in one global.bib file.
It has over 8400 entries and is automatically backed up.
Its size is not an issue in JabRef, Overleaf, or Emacs.

A similar automated PDF retrieval and relabeling system is available through Professor John Kitchin's [org-ref](https://github.com/jkitchin/org-ref) package for org-mode in Emacs.
This functionality is unavailable in Emacs for LaTeX-mode, hence my workaround solution with JabRef.

## Writing math equations

Overleaf does not support code snippets.
Emacs's [yasnippet](https://github.com/joaotavora/yasnippet) package eases the creation of snippets.
Snippets and especially the [LaTeX-auto-acitvating-snippets package](https://github.com/tecosaur/LaTeX-auto-activating-snippets) can ease the writing of equations.
The Swedish mathematician Mark Olson provides an [awesome demo](https://www.youtube.com/watch?v=5cGsiRtBK9I) of these features in a short video.

Overleaf is not the best environment for writing a lot of equations.
If snippets in Emacs are too overwhelming, use the GUI-driven equation editor in [LyX](https://www.lyx.org/) or use the free stand-a-lone [LaTeXiT.app](https://www.chachatelier.fr/latexit/) to typeset the math equations and paste the final code into your LaTeX document.
LaTeXiT enables you to store the equations in a library.
You can name the equations and add comments to them.
The library supports folders for organizing the equations into groups.
The library or a subset of it can be exported to a tex file.

## Text editors for LaTeX

Emacs has great support for writing in LaTeX.
For me, Vim was the penultimate editor, but Emacs is the ultimate one.
There is no more advanced editor.
Emacs is at the end of the text editor learning spiral.

## Know your math environments

One motivation for developing TeX (which evolved into LaTeX) was to provide better support for typesetting math equations.
There are numerous [equation environments](https://en.wikibooks.org/wiki/LaTeX/Advanced_Mathematics#Other_environments).
You should study them from time to time.
The LaTeX Wikibook is a good [resource](https://en.wikibooks.org/wiki/LaTeX).
Someday, I should read these two books.

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

As you may know, MathJax renders in web pages equations written in LaTeX.
You can left-click on the equation in the web page to see the tex code.
You can then copy and paste this code into a tex file and then use this code as a template.  

## How to deal with URLs that bleed into the right margin

Web addresses or URLs are frequently used to refer to resources on the World Wide Web.
URLs are useful to display because they can evolve.
Knowledge of an outdated URL can aid in the discovery of the current URL.
However, LaTeX does not know how to line-wrap URLs, so they can project into the right margin if they are long.

To address this problem, I put URLs in footnotes at the bottom of the page where they are out of the way.
I use the command `\footnote{\url{ }}`.
I have put this in a yasnippet snippet called *furl*.

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
I had mapped C-o to the yasnippet command for inserting a snippet; this is equivalent to using a tab with a tab trigger.
I did this to avoid conflicts with the use of TAB for tab completion elsewhere in Emacs.

Then the code in the snippet appears.
I paste the URL on the placeholder `http` and then hit the tab.
The cursor moves out of the braces and over the period to the start of the next sentence on a new line.
LaTeX automatically handles the generation of the footnote number and its placement in the footer of the page.
If the footnote bleeds into the right margin, you can remove the enclosed \url{} because, with this removed, \footnote can line wrap the URL.
Of course, in this state, the URL will not be a hyperlink to the website.


## Multipart documents

I can compile to PDF at a book with 1000 pages assembled from 400 individual documents, a table of contents, a bibliography, and an index in about a minute on Overleaf.com.
The same operation takes several minutes on my local computer.
A template for a daily logbook or diary for 2023 can be found [here](https://github.com/MooersLab/diary2023inLaTeX).
It has one tex file for each day of the year.

### main.tex for books

Books are best assembled from multiple documents, with one document per chapter.
This modularization eases the shuffling of the order of the chapters and the addition of new chapters.
It is super easy to shift lines of text up and down in Emacs.
This is done without using the mouse to make selections and copying and pasting to change the order.

Multipart documents require a *main.tex* file that I store at the top level of the project directory.
I use it to source a *0AAAcontents.tex* file (which has the *input* or *include* commands for importing the individual files for each chapter and appendix) and a mybookPreamble.tex that contains my preamble for books.
This modularization of the main.tex file has greatly eased debugging.

I frequently edit the *0AAAcontents.tex* file as I add chapters and appendices.
I named this file *0AAAcontents.tex* so that it appears at the top of the list of files in a `./Contents` folder where I store the chapter files and all other input files for the book.
I store the figures, code listings, and appendices in subfolders of `./Contents` to reduce the clutter.
I start the filename of chapters with `Ch` to distinguish them from other types of files.
I do not include chapter numbers in the filename of the chapter because their absolute position shifts over time.
I use the order of listing the *\include* commands in the *0AAAcontents.tex* file to automatically handle the numbering of the chapters.

The path to the main.tex file has to be included on the top line of each component file on Overleaf: `%!TEX root = ../main.tex` for Chapter files and `%!TEX root =  ../../main.tex` for the appendix files that are stored in the folder `./Contents/appendices`.
The percent sign is LaTeX's comment mark, so its presence in the first column of the first line is counterintuitive.

Similarly, four lines of code have to be at the end of each tex file for compiling by Emacs.
The code below works with the default LaTeX mode.
Alter the code when working with the Auctex package in Emacs rather than the built-in latex-mode package.
Some other editors, like TextMate, require similar metadata to find the master main.tex file.
The code at the top of the file for Overleaf and the code at the bottom of the file for Emacs can be present in the same file because they do not interfere with each other.

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
The $1 tab trigger is mirrored, so whatever you enter at the first site is propagated to the other sites.
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
% C-1 to close the current buffer.
% C-c y i to open a pop-up menu for selecting a snippet.
% C-c y for a hydra for yasnippets (Hydras are very cool! They save time. Learn about them.)
% Fn F1 to invoke a hydra for magic: mc for commit and mp for the push. Yes, use git inside an Emacs buffer that has opened a file under git version control.


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
The magit hydra came from this post on Emacs stackexchange [post](https://emacs.stackexchange.com/questions/21597/using-magit-for-the-most-basic-add-commit-push).
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
They are often added to figures, tables, equations, and code listings and then referred to from the text.
When reusing LaTeX code, it is too easy to propagate the same label and fail to add the reference to it.
Each label must be unique and referenced.
It is best to think of labels and references as being inseparable pairs.
Otherwise, you will spend much time dealing with labels that lack references during debugging.

## Add index keys as you write

The index entries are hyperlinked to the index keys in the final PDF.
It is all too easy to forget to add index keys.
However, they easily find information in the document.
It is best to add the index keys as you assemble the document to use them as you work on the project.
The keys serve as anchors to hyperlinks to them in the index.

The Acrobat Reader search function can lead to too many hits and is a poor substitute for using index keys.


## Use keybindings

Overleaf has standard CUA, Vim, and Emacs keybindings available.
You set the keybinding via the menu in the upper left-hand corner of the Overleaf webpage for a particular project.
The keybindings can be selected on a per-project basis.

## Image format

Use PNG files or PDFs for image files.
One drawback to Overleaf is that you cannot use postscript, EPS, or TIFF files.
You can take a snapshot of images in these formats and save them as PNG files for uploading to Overleaf.
You can also convert all the TIFF files in a folder to PNG files with the command `mogrify—format png *-Copy.tif`. 
The command line utility mogrify is installed with the imagemagick suite.
You can use PDFs, but unlike with PNG files, you will not get a preview of the image file on Overleaf.
You have to wait for the document to be compiled by Overleaf to see an included image from a PDF.

## Indices

LaTeX will autogenerate the table of contents, indices, bibliographies, glossaries, acronym lists, lists of figures, lists of tables, list of computer code listings, and lists of equations.
The last four lists require the use of captions that appear in the lists.
Captions require the use of a subset of environments that are known as floats.
I defined a *code* environment that encloses the minted environment for code listings and an *eqc* environment that does likewise for equations.
These custom float environments allow using captions with code listings and math expressions.

Computer RAM limits may block the generation of all of these indices.
You may have to drop several of them or find more RAM.
If you are using Overleaf, you can contact their tech support for help with this issue.

## Epigraphs

The epigraph package supports the insertion of epigraphs below the chapter title in a book.
I store quotes in a master epigraphs.tex file in one project.
I copy this file to other projects.

It takes a long time to gather good quotes.
I gather quotes over the years and call upon them when needed.
LaTeX automatically handles the formatting of the epigraph.

## Tables

Tables are a great strength of Markdown and org-mode because they are trivial to assemble.
In org mode, tables can do by-row and by-column computations like a spreadsheet.

In contrast, tables can be a pain to assemble in Emacs, unless you use a snippet for a table with a fixed number of rows and columns.
My collection of [LaTeX snippets](https://github.com/MooersLab/snippet-latex-mode) has several table templates.
There are also [web-tools](https://www.tablesgenerator.com/) that ease generating a template for a LaTeX table.

LaTeX can handle wide landscape orientation tables and long tables span multiple pages.

You can spend a lot of time configuring tables.
Beware that the publisher may not support fancy tables, so it is best to keep the table's format as simple as possible.


## Beamer package

The beamer package is used to assemble slideshows via LaTeX.
You can print notes with the slides for handouts.
It is easy to recycle a beamer slideshow when making a new one.
In my experience, assembling a slideshow in Beamer is faster than in PowerPoint because I can let LaTeX handle the positioning of figures and text.
This reduces the tedious use of the computer mouse to resize and position images, titles, and text boxes.

### Code listings in beamer slideshows
Code listings in beamer slides were tricky because the minted environments cannot be used directly, but once you figure it out, you can use the beamer slide as a template.
An example slideshow with code listings is found [here](https://github.com/MooersLab/slideshowTemplateLaTeX).

### Notes for each slide

Each slide is in a frame environment in a beamer tex file.
You can put whatever you want outside the frame environments.
I add the note environment for writing out the text of my talk.
This note environment can accommodate math expressions.
These notes can be printed out with the slides scaled down for handouts.

### Outline of the talk

Add a section key above each frame environment in the beamer file.
These will not interfere with compiling the beamer file, but they appear as an outline in the lower left corner of the webpage in Overleaf.
This outline can be navigated quickly to a distant frame in the slideshow.
This outline is helpful in organizing the order of the slides during the assembly of the slideshow.

### Movies are possible

Several latex packages support the use of animations.
Each frame of the animation has to be uploaded.
This a pain because of the large number of files involved, so I avoid animations.

### Hide the evidence that you are using beamer

Slides for five of my six courses and all my platform talks are in LaTeX.
I hide the icons that typify a beamer slideshow.
Most people think that I assembled my slides in PowerPoint.

## Posters via beamer

You can also assemble a poster in LaTeX by using one giant beamer slide.
I do cheat by using a giant PowerPoint to assemble the images. 
I export the PowerPoint slide as a PDF and import this into the top 4/5 of the beamer poster.
I place all text below this image in the bottom 1/5 of the poster.

Most posters have too much text. 
Nobody reads most of the text on most posters because there is too much text and it is too hard to concentrate in the roar of a poster session.
The text largely fails to ever serve its intended role.
The results, such as images, plots, and tables, are more important.
The poster is not a scientific paper; it is just a prop for a conversation.

The scientific paper has been around for 500 years.
The scientific poster has been around for 50 years.
This role of poster sessions was generated in response to a sudden glut of graduate students in the late 1960s and early 1970s in the United States. 
The sponsoring of poster sessions is now driven by tradition rather than a real need in this day and age of giant convention centers and virtual meetings that have few space constraints.

## Conclusions

LaTeX meets most of my writing needs.
Furthermore, LaTeX supports my pursuit of the [FAIR](https://www.go-fair.org/fair-principles/) principles.
I retain word processors on my computer to collaborate with colleagues who do not know LaTeX.

## Related projects of possible interest

- [LaTeX manuscript template](https://github.com/MooersLab/manuscriptInLaTeX/edit/main/README.md)
- [Writing log template](https://github.com/MooersLab/writingLogTemplate)
- [Slideshow Template](https://github.com/MooersLab/slideshowTemplateLaTeX)
- [Diary for 2022 in LaTeX](https://github.com/MooersLab/diary2022inLaTeX)
- [Diary for 2023 in LaTeX](https://github.com/MooersLab/diary2023inLaTeX)
- [latex-emacs profile](https://github.com/MooersLab/latex-emacs)
- [snippets for latex-mode in Emacs](https://github.com/MooersLab/snippet-latex-mode)
- [Quizzes about Emacs to improve recall of keybindings](https://github.com/MooersLab/qemacs)
- [Slides from talk about LaTeX in Emacs at the Berlin Emacs Meetup Aug 31, 2022](https://github.com/MooersLab/BerlinEmacsAugust2022)
- [Slides from talk about GhostText, Data Science Workshop, July 2022](https://github.com/MooersLab/DSW22ghosttext)
- [Video link to talk about GhostText, Data Science Workshop, July 2022](https://mediasite.ouhsc.edu/Mediasite/Channel/python/watch/4da0872f028c4255ae12935655e911321d)
- [The writer's law](https://github.com/MooersLab/thewriterslaw)

## Version History

|Version      | Changes                                               | Date            |
|:-----------:|:-----------------------------------------------------:|:---------------:|
| Version 0.2 | Added Update table to README.md                       | 2024 April 8    |

## Sources of Funding

- NIH: R01 CA242845
- NIH: R01 AI088011
- NIH: P30 CA225520 (PI: R. Mannel)
- NIH P20GM103640 and P30GM145423 (PI: A. West
