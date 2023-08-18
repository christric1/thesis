# DRL for Enhancing Object Detection Performance

## Requirements
* xelatex
* biber

## Recommended
* perl module Data::Lock  (to run the compile-thesis-from-scratch.pl script)
* emacs  (always recommended :)

## Usage
### Compile Document
    % perl compile-thesis-from-scratch.pl compile-opts.tex

or manually:

    % xelatex  -jobname thesis  compile-opts.tex
    % biber  thesis
    % xelatex  -jobname thesis  compile-opts.tex
    % xelatex  -jobname thesis  compile-opts.tex
    % makeindex  thesis.nlo  -s nomencl.ist  -o thesis.nls
    % xelatex  -jobname thesis  compile-opts.tex

Not all of that is usually necessary;__
if an edit does not affect citations, labels or nomenclature,  
just:

    % xelatex  -jobname thesis  compile-opts.tex

should be enough to update.


## File Summary

### Files Users Edit
    thesis.tex        Main thesis document.
    thesis.bib        To hold references
    config-opts.tex   Current compile options.  Better not to place it in git.

### Latex Formatting Files (users should not need to edit)
    PHlab-thesis.cls  class file.
    fonts-config.sty  configures fonts.
    frontmatter.tex   abstract, committee signature page, table of contents, nomenclature.

### Convenience Scripts
    compile-thesis-from-scratch.pl   Full compile from scratch.
    latex-cleanup-tempfiles.pl       Delete latex temp files.
