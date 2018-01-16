TARGET=newelln-decleenz_Sprint_Forward


default: pdf

bib: bib
	bibtex ${TARGET}


dvi: ${TARGET}.tex 
	#	run latex twice to get references correct
	latex ${TARGET}.tex
	#	you can also have a bibtex line here
	#	bibtex $(TARGET)
	latex $(TARGET).tex


ps: dvi
	dvips -R -Poutline -t letter ${TARGET}.dvi -o ${TARGET}.ps

pdf: ps
	ps2pdf ${TARGET}.ps


clean-dvi:
	rm -rf ${TARGET}.aux
	rm -rf ${TARGET}.log
	rm -rf ${TARGET}.dvi
	rm -rf ${TARGET}.out
	rm -rf ${TARGET}.toc


clean-ps: clean-dvi
	rm -rf ${TARGET}.ps


clean-pdf: clean-ps
	rm -rf ${TARGET}.bbl
	rm -rf ${TARGET}.blg
	rm -rf ${TARGET}.pdf


clean: clean-pdf

