### Makefile --- 

## Author: jpms
## Keywords: 
## X-URL: 

SHELL := /bin/csh

FIGS = $(wildcard figs/* plots/*)
TEXS = $(wildcard *.tex texfigs/*.tex tabs/*.tex algs/*.tex)
BIBS = $(wildcard *.bib)

all: r
#all: nopdftex

# Make memo
r: TRGT=memo

r: echo memo.pdf

echo:
	@echo "Making $(TRGT)"

clean:
	@latexmk -r .latexdefs -c

allclean: clean
	@-/bin/rm -f memo.pdf memo-*.pdf

%.pdf: %.tex $(TEXS) $(FIGS) $(BIBS)
	@echo "Building the pdf... 1"
	@latexmk -r .latexdefs -pdf $<
	@latexmk -r .latexdefs -c
	@cp -f $(TRGT).pdf $(TRGT)-$$cwd:h:t.pdf
	@echo "Done."

### Makefile ends here
