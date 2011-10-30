filename = document.tex
UNAME = "${shell uname}"
temp.tex : $(filename)
	if [ $(UNAME) = "Darwin" ]; then ( cp $(filename) temp.tex ) else ( nkf -e $(filename) > temp.tex ) fi
	platex temp.tex
	if [ $(UNAME) = "Darwin" ]; then ( dvipdfmx temp.dvi && open -a Preview temp.pdf ) else ( dvipdfmx temp.dvi && evince temp.pdf ) fi
	rm temp.log temp.dvi temp.aux temp.tex
all:
	make temp.tex



