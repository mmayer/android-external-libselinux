CFLAGS?=-O2 -Wall -fPIC

CPPFLAGS+=-I../include

libselinux_src_files := \
	booleans.c \
	canonicalize_context.c \
	disable.c \
	enabled.c \
	fgetfilecon.c \
	fsetfilecon.c \
	getenforce.c \
	getfilecon.c \
	getpeercon.c \
	lgetfilecon.c \
	load_policy.c \
	lsetfilecon.c \
	policyvers.c \
	procattr.c \
	setenforce.c \
	setfilecon.c \
	context.c \
	mapping.c \
	stringrep.c \
	compute_create.c \
	compute_av.c \
	avc.c \
	avc_internal.c \
	avc_sidtab.c \
	get_initial_context.c \
	checkAccess.c \
	sestatus.c \
	deny_unknown.c \
	callbacks.c \
	check_context.c \
	freecon.c \
	init.c \
	label.c \
	label_file.c \
	label_android_property.c
#	android.c

libselinux_src_obj := $(libselinux_src_files:.c=.o)

all: libselinux.a libselinux.so

libselinux.a: $(libselinux_src_obj)
	$(AR) r $@ $^

libselinux.so: $(libselinux_src_obj)
	$(CC) $^ -shared -o $@

.PHONY: clean
clean:
	rm -rf *.o *.a *.so
