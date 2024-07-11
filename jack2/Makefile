include $(TOPDIR)/rules.mk

PKG_NAME:=jack2
PKG_VERSION:=1.9.22
PKG_RELEASE:=1

PKG_SOURCE:=$(PKG_NAME)-$(PKG_VERSION).tar.gz
PKG_SOURCE_URL:=https://github.com/jackaudio/jack2/archive/v$(PKG_VERSION)
PKG_HASH:=skip

PKG_MAINTAINER:=Esa Aprilia Salsabila <esaapriliasalsabila@gmail.com>
PKG_LICENSE:=GPL-2.0 license
PKG_LICENSE_FILES:=COPYING

PKG_BUILD_DEPENDS:=python3/host
PKG_INSTALL:=1

include $(INCLUDE_DIR)/package.mk

define Package/jack2
	SECTION:=libs
	CATEGORY:=Libraries
	TITLE:=The Jack Audio Connection Kit
	DEPENDS:=+alsa-lib +libdbus +libexpat +libsamplerate +libsndfile +libncurses +libreadline
	URL:=https://github.com/jackaudio/jack2
endef

define Package/jack2/description
	JACK2 aka jackdmp is a C++ version of the JACK low-latency audio server for multi-processor machines.
	It is a new implementation of the JACK server core features that aims at removing some limitations of the JACK1 design.
	The activation system has been changed for a data flow model and lock-free programming techniques for graph access have been used to have a more dynamic and robust system.
endef

#CONFIGURE_CMD = ./waf

define Build/Compile
	cd $(PKG_BUILD_DIR); \
	./waf configure --prefix=/usr --libdir=/usr/lib --dbus --alsa --classic; \
	./waf build; \
	./waf --destdir="$(PKG_INSTALL_DIR)" install
endef

define Build/InstallDev
	$(INSTALL_DIR) \
	  $(1)/usr/include \
	  $(1)/usr/lib

	$(CP) \
	  $(PKG_INSTALL_DIR)/usr/include/jack \
	  $(1)/usr/include/

	$(CP) \
	  $(PKG_INSTALL_DIR)/usr/lib/{pkgconfig,jack,*.so*} \
	  $(1)/usr/lib/
endef

define Package/jack2/install
	$(INSTALL_DIR) \
	  $(1)/usr/bin \
	  $(1)/usr/lib

	$(CP) \
	  $(PKG_INSTALL_DIR)/usr/bin/* \
	  $(1)/usr/bin/
	$(CP) \
	  $(PKG_INSTALL_DIR)/usr/lib/{jack,*.so*} \
	  $(1)/usr/lib/
endef

$(eval $(call BuildPackage,jack2))
