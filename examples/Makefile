# show the manpage as text on stdout
text:  foo.1
	groff foo.1 -t -e -mandoc -Tascii | col -bx

# generate a .ps of the manpage
foo.ps: foo.1
	groff foo.1 -t -e -mandoc > foo.ps

# show the command-line help
help:
	(runhaskell -i../src Help.lhs --help)

# invoke Help.lhs and have it generate the man page source for us
foo.1: Help.lhs
	(runhaskell -i../src $< --dump-man-page  > $@)

clean:
	-rm -f foo.ps foo.1

.PHONY: clean text help

