UNAME = "${shell uname}"
elec.pdf : elec.dot
	dot2tex -tmath --debug --usepdflatex --autosize elec.dot > elec.tex
	#dot2tex -tmath --debug --autosize elec.dot > elec.tex
	# dot2tex -tmath --prog=circo --usepdflatex --autosize elec.dot > elec.tex
	# dot2tex -tmath --prog=neato --usepdflatex --autosize elec.dot > elec.tex
	# dot2tex -tmath --autosize elec.dot | sed -e s/documentclass/documentclass[papersize]/ > elec.tex

	# circo -Txdot elec.dot | dot2tex -tmath --autosize > elec.tex
	pdflatex elec.tex -o elec.pdf
	# platex elec.tex
	# dvips elec.dvi
	# dvipdf elec.dvi
	if [ $(UNAME) = "Darwin" ]; then ( open -a Preview elec.pdf ) else ( evince elec.pdf ) fi
