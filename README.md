# UWMadison Beamer Template

Original Repository: https://github.com/travitch/uw-beamer-template  

This is a Beamer template set up to look pretty decent and have an University of Wisconsin-Madison theme.
It is, of course, better than the existing Powerpoint templates.

The easiest way to install this theme is to just dump the *.sty files into the same directory as your tex source.

The theme options are follow:
  * nav          - This option includes a navigation bar in the
                   lower-right corner of each slide
  * white        - This option changes the color scheme to black-on-white
                   for projectors with poor color balance
  * nologo       - Suppress the crest in frame titles
  * compactlogo  - Compact title logo (takes less vertical space)


Other suggested packages:
* tikz (pgf, for diagrams)
* listings (for source code listings)
* fontspec (if using xetex)

Additionally, The template that can be used as a starting point of making presentation has been included.  
This template is originally made by [Overleaf](https://www.overleaf.com/learn/latex/beamer).


## Extra

Here is a very handy snippet of TeX to stick at
the beginning of your presentation (after \begin{document}):

```
\newcommand*{\alphabet}{ABCDEFGHIJKLMNOPQRSTUVWXYZabcdefghijklmnopqrstuvwxyz}
\newlength{\highlightheight}
\newlength{\highlightdepth}
\newlength{\highlightmargin}
\setlength{\highlightmargin}{2pt}
\settoheight{\highlightheight}{\alphabet}
\settodepth{\highlightdepth}{\alphabet}
\addtolength{\highlightheight}{\highlightmargin}
\addtolength{\highlightdepth}{\highlightmargin}
\addtolength{\highlightheight}{\highlightdepth}
\newcommand*{\Highlight}{\rlap{\textcolor{HighlightBackground}{\rule[-\highlightdepth]{\linewidth}{\highlightheight}}}}
```

HighlightBackground is defined by the Wisconsin theme. 
This snippet allows you to include source code listings in the following way:

```
  \lstinputlisting[language=C,moredelim={**[il][\Highlight]{@}}]{file.c}
```

Note the moredelim option; with this option and the preceeding declarations, prefixing a line in file.c will highlight the line.

