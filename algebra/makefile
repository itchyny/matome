UNAME = "${shell uname}"
algebra.pdf : algebra.dot
	cat algebra.dot | \
		sed 's/\/\/.*//g' | \
		sed 's/{/OPENPAREN/g' | \
		sed 's/}/CLOSEPAREN/g' | \
		sed 's/\\/BACKSLASH/g' | \
		cpp-4.5 -P -C | \
		sed 's/BACKSLASH/\\/g' | \
		sed 's/OPENPAREN/{/g' | \
		sed 's/CLOSEPAREN/}/g' > temp.dot
	dot2tex -tmath --debug --usepdflatex --autosize temp.dot > temp.tex
	#dot2tex -tmath --debug --autosize temp.dot > temp.tex
	# dot2tex -tmath --prog=circo --usepdflatex --autosize temp.dot > temp.tex
	# dot2tex -tmath --prog=neato --usepdflatex --autosize temp.dot > temp.tex
	# dot2tex -tmath --autosize temp.dot | sed -e s/documentclass/documentclass[papersize]/ > temp.tex

	# circo -Txdot temp.dot | dot2tex -tmath --autosize > temp.tex
	# convert -density 250 elec.pdf elec.jpg
	# platex temp.tex
	# dvipdfm temp.dvi
	pdflatex temp.tex  temp.pdf
	# rm ./dot2tex.log ./temp.aux ./temp.log
	if [ $(UNAME) = "Darwin" ]; then ( open -a Preview temp.pdf ) else ( evince temp.pdf ) fi

all:
	make algebra.pdf
