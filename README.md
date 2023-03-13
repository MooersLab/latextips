# Tips for greater productivity with LaTeX

This is a summary of advice gleaned from a decade of using LaTeX. 

## Start with Overleaf 

Overleaf.com provides free accounts. You only need the professional account if you are doing collaborative writing. The documentation about LaTeX on the Overleaf website is excellent. Your writing project will be accessible from your multiple devices. The built-in support for debugging is excellent. Overleaf compiles your document to PDF very quickly and painlessly.

## Use version control 

Each Overleaf project has its own git repository. You can git clone your project to your local computer. Take care not to get the two versions out of synch while writing or editing.

## Use bookmark bar 

The URL of the writing project can be added to the browser toolbar for rapid access.

## Start with simple projects

There is not that much in the way of coding to learn for writing the heart of a document between the begin document and end document statement. The trouble comes when you are extending LaTeX with packages.

## Start with simple manuscript format

Avoid the complex template documents for journal articles on Overleaf at first. You can submit a plain double-spaced manuscript document on the first submission for any journal. DO not waste time on complex configurations for the first submission. You have to send the manuscript to a different journal.

## Write one sentence per line

This style of writing eases version control with git (Impossible with Word documents). It also eases the shuffling of sentences during rewriting. Each reason alone is sufficient to use it. The *twautex* package in Emacs eases writing one sentence per line. It is one GitHub.

## Use JabRef to manage a global.bib file

JabRef.app is a free, open-source Java-based stand-a-lone application for managing and searching your Bibtex file. It has tools for finding duplicate entries and damaged entries. A JabRef plugin for web browsers is available that will send the bibtex info to JabRef and download, relabel, and file the associated PDF when on a PubMed, Arvix, or some journal webpage for an article. I have JabRef configured to relabel the PDF with the citekey. My citekey is `FirstAuthorLastNameYearTitle'. The citekey has no dashes or underscores or whitespaces. The title is in Camel case.  You quickly get used to reading CamelCase. I click the generate-key button in JabRef to autogenerate the citekey for an entry. I store all of the bibtex entries in one global.bib file. It has 7100 entries and is automatically backed up. A similar automated PDF retrieval and relabeling system is available through John Kitchin's org-ref package for org-mode. It is not available in Emacs for LaTeX-mode, hence my work around solution with JabRef.

## Use Emacs for writing math equations

Overleaf does not support code snippets. Emacs's yasnippet package supports eases creation of snippets. Emacs has great support for writing in LaTeX. Snippets and especially the auto-snippet package can ease the writing of equations. Overleaf is not best environment for writing a lot of equations. If Emacs is overwhelming, use the GUI-driven equation editor in LyX or use the LaTeXiT.app to typeset the math equations.

## Multipart documents

I can compile to PDF at 370 part book with 1000 pages, a table of contents, bibliography, and index in about a minute on overleaf and several minutes on my local computer.

## main.tex

Multipart documents require a main.tex file. I use it to source a 0AAAcontents.tex file for the imported files and the a mybookPreamble.tex that contains my preamble for books. This modularization greatly eased debugging. The path to the main.tex file has to be included on the top line of each component file. Similarly, four lines of code have to be at the end of each tex file for compiling by Emacs.

## Reference all labels

When reusing code, it is too easy to propagate the same label. Each label must be unique, and it must be referenced.

## Use keybindings

Overleaf has standard (CUA), Vim, and Emacs keybindings available. Select one set and master them.

## Image format

Use PNG files or PDFs. One drawback to Overleaf is that you cannot use postscript, EPS, or TIFF files. You can use PDFs, but you will not get a preview of the image file. You have to wait for the document to be compiled by Overleaf.

## Indices

You can autogenerate table of contents, indices, bibliographies, glossaries, acronym lists, lists of figures, lists of tables, list of computer code listings, and list of equations. The last four lists require the use of captions. Captions require the use of float environments. I defined a code environment that encloses the minted environment for code listings and an eqc environment for equations with captions. There may be computer RAM limits that block the generation of all of these lists. You may have to drop several of them.

## Epigraphs

The epigraph package supports the insertion of epigraphs, which I store in a epigraphs.tex file. I gather quotes over the years and call upon them when needed. LaTeX automatically handles the formatting.

## Tables

Tables are great a strength of org-mode and a great weak spot for LaTeX. You can spend a lot of time configuring tables in LaTeX. There are web-tools that ease generating a template for a table. Beware that the publisher may not support fancy tables, so it is best to get the format simple.

## Beamer package

The beamer package is used to assemble slideshows via LaTeX. You can print notes with the slides for handouts. It is easy to recycle a beamer slideshow when making a new one. You can also assemble a poster in LaTeX by using one giant beamer slide. Slides for five of my six courses and all of my platform talks are in LaTeX. I hide the icons that typify a beamer slideshow. Most people think that I assembled my slides in PowerPoint.
