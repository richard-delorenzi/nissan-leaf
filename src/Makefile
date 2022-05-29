.SILENT:
#.SECONDEXPANSION:
.DELETE_ON_ERROR:

parts = intro.md mk1.md mk2.md range-standards.md

../output/%.html:%.md
	markdown $< >$@

../output/Readme.md: $(parts)
	cat $+ >$@
