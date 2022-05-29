#.SILENT:
#.SECONDEXPANSION:
.DELETE_ON_ERROR:

md_parts = intro.md mk1.md mk2.md range-standards.md
html_parts = head.html Readme.md footer.md foot.html

index.html: $(html_parts)
	echo >$@
	cat head.html >>$@
	echo '<main>' >>$@
	markdown Readme.md >>$@
	echo '</main>' >>$@
	echo '<footer>' >>$@
	markdown footer.md >>$@
	echo '</footer>' >>$@
	cat foot.html >>$@

Readme.md: $(md_parts)
	cat $+ >$@

../output/%:%
	cp -T $< $@

%.html:%.md
	markdown $< >$@
