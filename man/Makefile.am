.0.1:
	@sed -e "s/!VERSION!/@PACKAGE_VERSION@/g" < $*.0 > $@
if WITH_SOURCE_DATE_EPOCH
	@sed -e "s/!DATE!/`LC_ALL=C date --utc --date="@$(SOURCE_DATE_EPOCH)" '+%B %Y'`/g" < $*.0 > $@
else
	@sed -e "s/!DATE!/`date '+%B %Y'`/g" < $*.0 > $@
endif
	@echo Built $*.1 from template

manpages_in_files = $(wildcard *.0)
manpages_built    = $(patsubst %.0,%.1,$(manpages_in_files))

man1_MANS = $(manpages_built)

EXTRA_DIST = $(manpages_in_files)

CLEANFILES = $(manpages_built)
