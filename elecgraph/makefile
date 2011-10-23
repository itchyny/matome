UNAME = "${shell uname}"
elecgraph.pdf : elecgraph.dot
	dot2tex -tmath --debug --usepdflatex --autosize elecgraph.dot > elecgraph.tex
	#dot2tex -tmath --debug --autosize elecgraph.dot > elecgraph.tex
	# dot2tex -tmath --prog=circo --usepdflatex --autosize elecgraph.dot > elecgraph.tex
	# dot2tex -tmath --prog=neato --usepdflatex --autosize elecgraph.dot > elecgraph.tex
	# dot2tex -tmath --autosize elecgraph.dot | sed -e s/documentclass/documentclass[papersize]/ > elecgraph.tex

	# circo -Txdot elecgraph.dot | dot2tex -tmath --autosize > elecgraph.tex
	pdflatex elecgraph.tex -o elecgraph.pdf
	rm ./dot2tex.log ./elecgraph.aux ./elecgraph.log
	if [ $(UNAME) = "Darwin" ]; then ( open -a Preview elecgraph.pdf ) else ( evince elecgraph.pdf ) fi

all:
	make elecgraph.pdf
