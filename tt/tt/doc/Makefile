# Paquetes necesarios (Arch Linux)
# texlive-most texlive-lang biber
# Para Ubuntu/Debian
# texlive-full
# Y para windows o mac, MIKTEX o Texlive

.DEFAULT_GOAL := default

FLAGS = --shell-escape

default: references

release: references
	pdflatex $(FLAGS) main

refs: references
references: dirty
	biber main
	makeindex main.glo -s main.ist -t main.glg -o main.gls
	pdflatex $(FLAGS) main

dirty: Makefile
	pdflatex $(FLAGS) main

c: clean
clean:
	rm -f *.aux *.bbl *.bcf *.blg *.log *.pdf *.xml *.toc *.pyg *.out *.glo *.ist *.glg *.gls
	rm -f preamble/*.aux
	rm -f img/*.pdf
	rm -rf ./_minted-main
