EXTRA_DIST =

AM_CFLAGS = \
  $(XORG_SERVER_CFLAGS) \
  $(XRDP_CFLAGS) \
  -I$(top_srcdir)/module

xrdpdev_drv_la_LTLIBRARIES = xrdpdev_drv.la

xrdpdev_drv_la_LDFLAGS = -module -avoid-version

xrdpdev_drv_ladir = $(moduledir)/drivers

xrdpdev_drv_la_SOURCES = xrdpdev.c

xrdpdev_drv_la_LIBADD =

xrdpdevsysconfdir=$(sysconfdir)/X11/xrdp

dist_xrdpdevsysconf_DATA = \
  xorg.conf

sbin_SCRIPTS = xorgxrdp

SUBST_VARS = sed \
   -e 's|@PACKAGE_VERSION[@]|$(PACKAGE_VERSION)|g' \
   -e 's|@xrdpdevsysconfdir[@]|$(xrdpdevsysconfdir)|g'

subst_verbose = $(subst_verbose_@AM_V@)
subst_verbose_ = $(subst_verbose_@AM_DEFAULT_V@)
subst_verbose_0 = @echo "  SUBST    $@";

SUFFIXES = .in
.in:
	$(subst_verbose)$(SUBST_VARS) $< > $@

CLEANFILES = $(sbin_SCRIPTS)
