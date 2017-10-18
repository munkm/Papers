###################################################################
# Name of master .tex file for thesis 
manuscript = char_paper
bibliography = bibliography
export TEXINPUTS:=.:${TEXINPUTS}
export BSTINPUTS:=.:${BSTINPUTS}

# name of build directory for thesis
bdir=compile

# compilation options
latexopt = -halt-on-error -file-line-error -output-directory=$(bdir)

###################################################################
#     make all
###################################################################

all: $(manuscript).pdf

$(manuscript).pdf: $(manuscript).tex $(bibliography).bib
	mkdir -p $(bdir)
	pdflatex $(latexopt) $(manuscript)
	bibtex    $(bdir)/$(manuscript)
	pdflatex $(latexopt) $(manuscript)
	pdflatex $(latexopt) $(manuscript)



###################################################################
#     make clean
###################################################################

clean:
	rm -fr $(bdir)
	find . -name "*.aux" -delete 

.PHONY: all clean
