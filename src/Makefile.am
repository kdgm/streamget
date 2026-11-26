

bin_PROGRAMS = \
	streamget

streamget_SOURCES = \
	lock.h \
	lock.c \
	daemonize.h \
	daemonize.c \
	url_fopen.h \
	url_fopen.c \
	main.c

BUILT_SOURCES = \
	git-ref.h
	
# HEAD is detached in CI and when building a tag, so do not go through the branch ref
GIT_REF = $(shell git rev-parse --short HEAD 2>/dev/null)

git-ref.h: FORCE
	echo "#define GIT_REF \"$(GIT_REF)\"" > git-ref.h
	
FORCE:
	
CLEANFILES = $(BUILT_SOURCES)

streamget_LDADD = @LIBCURL@

