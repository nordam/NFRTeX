.PHONY: all show clean force

target = ResearcherProject
bibliography = references

compiler = pdflatex
flags = -file-line-error -halt-on-error

all: $(target).pdf

show: all
	open $(target).pdf

$(target).pdf: $(target).tex $(bibliography).bib
	$(compiler) $(flags) $(target)
	bibtex $(target)
	$(compiler) $(flags) $(target)
	$(compiler) $(flags) $(target)

force:
	$(compiler) $(flags) $(target)
	bibtex $(target)
	$(compiler) $(flags) $(target)
	$(compiler) $(flags) $(target)

clean:
	rm -f $(target).dvi $(target).ps
	rm -f $(target).aux $(target).log $(target).toc
	rm -f $(target).bbl $(target).blg $(target).out
