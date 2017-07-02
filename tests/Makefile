TESTINPUTS := $(wildcard *.tex)
TESTINPUTS := $(patsubst test2e.tex,,$(TESTINPUTS))
TESTINPUTS := $(patsubst testpl2e.tex,,$(TESTINPUTS))
TESTDVIOUTPUTS := $(patsubst %.tex,%.dvi,$(TESTINPUTS))
TESTPDFOUTPUTS := $(patsubst %.tex,%.pdf,$(TESTINPUTS))
#TESTLVTINPUTS := $(patsubst %.tex,%.lvt,$(TESTINPUTS))
#TESTLOGOUTPUTS := $(patsubst %.tex,%.log,$(TESTINPUTS))
KANJI = -kanji=utf8
FONTMAP = -f ipaex.map -f ptex-ipaex.map

.PHONY: test testpdf testdvi testlog clean
test: testdvi #testlog

testdvi: $(TESTDVIOUTPUTS)
testpdf: $(TESTPDFOUTPUTS)
#testlog: $(TESTLOGOUTPUTS)

%.dvi:
	platex $(KANJI) $*.tex
	platex $(KANJI) $*.tex
	platex $(KANJI) $*.tex
%.pdf:
	dvipdfmx $(FONTMAP) $*.dvi

clean:
	rm -f *.dvi *.log *.aux *.toc *.out *.pdf
