md_parts = intro.md mk1.md mk2.md range-standards.md
html_parts = head.html main.html footer.md foot.html

.SILENT:
#.SECONDEXPANSION:
.DELETE_ON_ERROR:
.SECONDARY:

main_parts = $(addsuffix .html, $(basename ${md_parts}))

index.html: $(html_parts)
	@echo building $@
	echo >$@
	cat head.html >>$@
	echo '<main>' >>$@
	cat main.html >>$@
	echo '</main>' >>$@
	echo '<footer>' >>$@
	markdown footer.md >>$@
	echo '</footer>' >>$@
	cat foot.html >>$@

main.html: ${main_parts}
	@echo building $@
	cat $+ >$@

Readme.md: ${md_parts}
	@echo building $@
	cat $+ >$@

../output/%:%
	@echo building $@
	cp -T $< $@

%.html:%.md
	@echo building $@
	echo >$@
	markdown $< >>$@
