UNAME = "${shell uname}"
elec_magnetic.pdf : elec_magnetic.tex
	platex elec_magnetic.tex
	dvipdfmx elec_magnetic.dvi
	if [ $(UNAME) = "Darwin" ]; then ( open -a Preview elec_magnetic.pdf ) else ( evince elec_magnetic.pdf ) fi
all:
	make elec_magnetic.pdf



