md_parts = intro.md mk1.md mk2.md range-standards.md
html_parts = head.html main.html footer.html foot.html
main_parts = mk1.html mk2.html
aside_parts = range-standards.html
nav_parts = intro.html

.SILENT:
#.SECONDEXPANSION:
.DELETE_ON_ERROR:
.SECONDARY:

index.html: $(html_parts)
	@echo building $@
	cat $+ >$@

main.html: ${nav_parts} ${main_parts} ${aside_parts}
	@echo building $@
	echo >$@
	echo '<main>' >>$@
	cat $+ >>$@
	echo '</main>' >>$@

footer.html: footer.md
	@echo building $@
	echo >$@
	echo '<footer>' >>$@
	markdown $< >>$@
	echo '</footer>' >>$@

%.html:%.md
	@echo building $@
	echo >$@
	echo '<section id="$(basename $@)">' >>$@
	markdown $< >>$@
	echo '</section>' >>$@

Readme.md: ${md_parts}
	@echo building $@
	cat $+ >$@

../output/%:%
	@echo building $@
	cp -T $< $@
