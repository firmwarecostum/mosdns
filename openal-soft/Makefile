include $(TOPDIR)/rules.mk

PKG_NAME:=openal-soft
PKG_VERSION:=1.23.1
PKG_RELEASE:=1

PKG_SOURCE:=$(PKG_NAME)-$(PKG_VERSION).tar.bz2
PKG_SOURCE_URL:=https://github.com/kcat/openal-soft/releases/download/$(PKG_VERSION)
PKG_HASH:=skip

PKG_MAINTAINER:=Esa Aprilia Salsabila <esaapriliasalsabila@gmail.com>
PKG_LICENSE:=License
PKG_LICENSE_FILES:=COPYING

CMAKE_BINARY_SUBDIR := build

PKG_BUILD_PARALLEL:=1
PKG_INSTALL:=1

include $(INCLUDE_DIR)/package.mk
include $(INCLUDE_DIR)/cmake.mk

define Package/openal-soft
	SECTION:=libs
	CATEGORY:=Libraries
	TITLE:=OpenAL Soft is a software implementation of the OpenAL 3D audio API.
	DEPENDS:=+libatomic +libstdcpp +alsa-lib +libsndfile +portaudio +pulseaudio-daemon
	URL:=https://github.com/kcat/openal-soft
endef

define Package/openal-soft/description
	OpenAL Soft is an LGPL-licensed, cross-platform, software implementation of the OpenAL 3D audio API. It's forked from the open-sourced Windows version available originally from openal.org's SVN repository (now defunct).
	OpenAL provides capabilities for playing audio in a virtual 3D environment. Distance attenuation, doppler shift, and directional sound emitters are among the features handled by the API.
	More advanced effects, including air absorption, occlusion, and environmental reverb, are available through the EFX extension. It also facilitates streaming audio, multi-channel buffers, and audio capture.
endef

CMAKE_OPTIONS += \
	-DALSOFT_UPDATE_BUILD_VERSION=OFF

define Build/InstallDev
	$(INSTALL_DIR) \
	  $(1)/usr/include \
	  $(1)/usr/lib \
	  $(1)/usr/share

	$(CP) \
	  $(PKG_INSTALL_DIR)/usr/include/AL \
	  $(1)/usr/include/

	$(CP) \
	  $(PKG_INSTALL_DIR)/usr/lib/{pkgconfig,*.so*,cmake} \
	  $(1)/usr/lib/

	$(CP) \
	  $(PKG_INSTALL_DIR)/usr/share/openal \
	  $(1)/usr/share/
endef

define Package/openal-soft/install
	$(INSTALL_DIR) \
	  $(1)/usr/bin \
	  $(1)/usr/lib \
	  $(1)/usr/share

	$(CP) \
	  $(PKG_INSTALL_DIR)/usr/bin/* \
	  $(1)/usr/bin/

	$(CP) \
	  $(PKG_INSTALL_DIR)/usr/lib/*.so* \
	  $(1)/usr/lib/

	$(CP) \
	  $(PKG_INSTALL_DIR)/usr/share/openal \
	  $(1)/usr/share/
endef

$(eval $(call BuildPackage,openal-soft))
