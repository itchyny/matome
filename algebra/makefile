UNAME = "${shell uname}"

all:
	make algebra.pdf

temp.dot : algebra.dot
	cat algebra.dot | \
		sed 's/\/\/.*//g' | \
		sed 's/{/OPENPAREN/g' | \
		sed 's/}/CLOSEPAREN/g' | \
		sed 's/\\/BACKSLASH/g' | \
		sed "s/\'/QUOTE/g" | \
		cpp-4.2 | \
		perl -pe 's/NEWLINE/\n/g' | \
		cpp-4.2 | \
		sed "s/QUOTE/\'/g" | \
		sed 's/BACKSLASH/\\/g' | \
		sed 's/OPENPAREN/{/g' | \
		sed 's/CLOSEPAREN/}/g' > temp.dot

temp.pdf : algebra.dot
	make temp.dot
	dot2tex -tmath --debug --usepdflatex --autosize temp.dot > temp.tex
	pdflatex temp.tex  temp.pdf

algebra.pdf : algebra.dot
	cat dotinit_base.dot > dotinit.dot
	echo "#define SET_GROUP 1" >> dotinit.dot && make temp.pdf
	rm ./dot2tex.log ./temp.aux ./temp.log
	if [ $(UNAME) = "Darwin" ]; then ( open -a Preview temp.pdf ) else ( evince temp.pdf ) fi
	mv temp.pdf algebra0.pdf



