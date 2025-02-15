include $(TOPDIR)/rules.mk

PKG_NAME:=hamlib
PKG_VERSION:=4.5.5
PKG_RELEASE:=1

PKG_SOURCE_URL:=https://github.com/Hamlib/Hamlib/releases/download/$(PKG_VERSION)
PKG_SOURCE:=$(PKG_NAME)-$(PKG_VERSION).tar.gz
PKG_HASH:=skip

PKG_MAINTAINER:=Esa Aprilia Salsabila <esaapriliasalsabila@gmail.com>
PKG_LICENSE:=License GPL-2.0 license
PKG_LICENSE_FILES:=COPYING COPYING.LIB

PKG_BUILD_DEPENDS:=swig/host lua5.3/host

PKG_BUILD_PARALLEL:=1
PYTHON3_PKG_BUILD:=0
PKG_INSTALL:=1

include $(INCLUDE_DIR)/package.mk
include $(TOPDIR)/feeds/packages/lang/python/python3-package.mk

define Package/hamlib
	SECTION:=libs
	CATEGORY:=Libraries
	TITLE:=Ham radio control library for rigs, rotators, tuners, and amplifiers
	DEPENDS:=+libusb-1.0 +libreadline +libxml2 +libstdcpp +tcl +lua5.3 +python3
	URL:=https://github.com/Hamlib/Hamlib
endef

define Package/hamlib/description
	The library provides functions for both radio and rotator control, and data retrieval from the radio or rotator.
	A number of functions useful for calculating distance and bearing and grid square conversion are included.
endef

CONFIGURE_VARS += \
	LUA="$(STAGING_DIR_HOSTPKG)/bin/lua5.3" \
	LUA_INCLUDE="-I$(STAGING_DIR)/usr/include/lua5.3" \
	LUA_LIB="-L$(STAGING_DIR)/usr/lib -llua5.3" \
	PYTHON="$(STAGING_DIR_HOSTPKG)/bin/$(PYTHON3)"

CONFIGURE_ARGS += \
	--enable-shared \
	--disable-static \
	--with-xml-support \
	--without-cxx-binding \
	--without-perl-binding \
	--with-python-binding \
	--with-tcl-binding \
	--with-lua-binding

define Build/InstallDev
	$(INSTALL_DIR) \
	  $(1)/usr/include \
	  $(1)/usr/lib \
	  $(1)/usr/share

	$(CP) \
	  $(PKG_INSTALL_DIR)/usr/include/hamlib \
	  $(1)/usr/include/

	$(CP) \
	  $(PKG_INSTALL_DIR)/usr/lib/{pkgconfig,*.so*} \
	  $(1)/usr/lib/

	$(CP) \
	  $(PKG_INSTALL_DIR)/usr/share/aclocal \
	  $(1)/usr/share/
endef

define Package/hamlib/install
	$(INSTALL_DIR) \
	  $(1)/usr/bin \
	  $(1)/usr/lib \
	  $(1)/$(PYTHON3_PKG_DIR)

	$(CP) \
	  $(PKG_INSTALL_DIR)/usr/bin/* \
	  $(1)/usr/bin/

	$(CP) \
	  $(PKG_INSTALL_DIR)/usr/lib/{lua,tcl,*.so*} \
	  $(1)/usr/lib/

	$(CP) \
	  $(PKG_INSTALL_DIR)/$(PYTHON3_PKG_DIR)/* \
	  $(1)/$(PYTHON3_PKG_DIR)/
endef

$(eval $(call BuildPackage,hamlib))
