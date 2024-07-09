include $(TOPDIR)/rules.mk

PKG_NAME:=groff
PKG_VERSION:=1.23.0
PKG_RELEASE:=1

PKG_SOURCE:=$(PKG_NAME)-$(PKG_VERSION).tar.gz
PKG_SOURCE_URL:=https://ftp.gnu.org/gnu/groff/
PKG_HASH:=skip

PKG_MAINTAINER:=Esa Aprilia Salsabila <esaapriliasalsabila@gmail.com>
PKG_LICENSE:=GPL-3.0-or-later
PKG_LICENSE_FILES:=COPYING

PKG_HOST_ONLY:=1
HOST_BUILD_DEPENDS:=perl/host
HOST_BUILD_PARALLEL:=1

include $(INCLUDE_DIR)/package.mk
include $(INCLUDE_DIR)/host-build.mk

define Package/groff
  SECTION:=lang
  CATEGORY:=Languages
  TITLE:=GNU troff text-formatting system
  URL:=https://www.gnu.org/software/groff/groff.html
  BUILDONLY:=1
endef

define Package/groff/description
  groff (GNU roff) is a typesetting system that reads plain text input files that include formatting commands to produce output in PostScript, PDF, HTML, or DVI formats or for display to a terminal.
  Formatting commands can be low-level typesetting primitives, macros from a supplied package, or user-defined macros. All three approaches can be combined.
endef

HOST_CONFIGURE_ARGS += \
	--disable-shared \
	--without-x

$(eval $(call HostBuild))
$(eval $(call BuildPackage,groff))
