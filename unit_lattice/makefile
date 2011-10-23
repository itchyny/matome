UNAME = "${shell uname}"
unit_lattice.pdf : unit_lattice.tex
	platex unit_lattice.tex
	dvipdfmx unit_lattice.dvi
	rm unit_lattice.dvi unit_lattice.aux unit_lattice.log
	if [ $(UNAME) = "Darwin" ]; then ( open -a Preview unit_lattice.pdf ) else ( evince unit_lattice.pdf ) fi
all:
	make unit_lattice.pdf



