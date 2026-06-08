# ============================================================
# Makefile  –  Template PPGCC UFERSA/UERN
# ============================================================
# Uso:
#   make          → compila dissertacao.pdf completo
#   make quick    → compilação rápida (1 passagem, sem bib)
#   make clean    → remove arquivos auxiliares
#   make cleanall → remove tudo inclusive o PDF

DOC = dissertacao
LATEX = pdflatex
BIBTEX = bibtex
FLAGS = -interaction=nonstopmode -halt-on-error

.PHONY: all quick clean cleanall

all: $(DOC).pdf

$(DOC).pdf: $(DOC).tex
	$(LATEX) $(FLAGS) $(DOC)
	$(BIBTEX) $(DOC)
	$(LATEX) $(FLAGS) $(DOC)
	$(LATEX) $(FLAGS) $(DOC)

quick:
	$(LATEX) $(FLAGS) $(DOC)

clean:
	rm -f *.aux *.bbl *.blg *.log *.lot *.lof *.out \
	      *.toc *.idx *.ind *.ilg *.glo *.gls \
	      *.synctex.gz *.fls *.fdb_latexmk \
	      capitulos/*.aux pre-textuais/*.aux \
	      pos-textuais/*.aux pos-textuais/apendices/*.aux \
	      pos-textuais/anexos/*.aux

cleanall: clean
	rm -f $(DOC).pdf
