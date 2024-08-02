### Makefile --- 

## Author: jpms
## Keywords: 
## X-URL: 

FIGS = $(wildcard figs/* plots/*)
TEXS = $(wildcard *.tex text/*.tex cfg/*.tex texfigs/*.tex tables/*.tex algs/*.tex)
BIBS = $(wildcard bib/*.bib)

all: r
#all: nopdftex

# Make paper
r: TRGT=paper

r: echo paper.pdf

echo:
	@echo "Making $(TRGT)"

clean:
	@latexmk -r .latexdefs -c
	@rm -f paper.vtc

allclean: clean
	@-/bin/rm -f paper.pdf

%.pdf: %.tex $(TEXS) $(FIGS) $(BIBS)
	@echo "Building the pdf... 1"
	@latexmk -xelatex -r .latexdefs -pdf $<
	@latexmk -r .latexdefs -c
	@rm -f $(TRGT).vtc comment.cut
	@echo "Done."

### Makefile ends here
