all: knitr pdf

knitr:
	RScript knit.R evaluation.Rnw gen-eval.tex

pdf:
	pdflatex paper.tex
	pdflatex paper.tex
