include $(TOPDIR)/rules.mk

PKG_NAME:=aprx
PKG_VERSION:=2.9.1
PKG_RELEASE:=1

PKG_SOURCE:=$(PKG_NAME)-$(PKG_VERSION).tar.gz
PKG_SOURCE_URL:=https://thelifeofkenneth.com/aprx/release/
PKG_HASH:=skip

PKG_MAINTAINER:=Esa Aprilia Salsabila <esaapriliasalsabila@gmail.com>
PKG_LICENSE:=BSD-3-Clause license
PKG_LICENSE_FILES:=LICENSE

PKG_BUILD_DEPENDS:=libax25 perl/host
PKG_FIXUP:=autoreconf
PKG_INSTALL:=1

include $(INCLUDE_DIR)/package.mk

define Package/aprx
	SECTION:=net
	CATEGORY:=Network
	TITLE:=A highly configurable APRS I-gate/Digipeater Daemon
	DEPENDS:=+libstdcpp +libpthread
	URL:=https://thelifeofkenneth.com/aprx/
endef

define Package/aprx/description
	Aprx is a software package designed to run on any POSIX platform (Linux/BSD/Unix/etc.) and act as an APRS Digipeater and/or Internet Gateway.
	Aprx is able to support most APRS infrastructure deployments, including single stand-alone digipeaters, receive-only Internet gateways, full RF-gateways for bi-directional routing of traffic, and multi-port digipeaters operating on multiple channels or with multiple directional transceivers.
endef

define Package/aprx/conffiles
/etc/aprx.conf
endef

TARGET_CFLAGS  += -fcommon -O2 -DERLANGSTORAGE

CONFIGURE_ARGS += \
	--prefix=/usr \
	--sysconfdir=/etc \
	--with-pthread

define Build/Compile
	$(call Build/Compile/Default,LD=$(TARGET_CC))
endef

define Package/aprx/install
	$(INSTALL_DIR) \
	  $(1)/etc \
	  $(1)/usr/sbin

	$(CP) \
	  $(PKG_INSTALL_DIR)/etc/aprx.conf \
	  $(1)/etc/aprx.conf
	$(CP) \
	  $(PKG_INSTALL_DIR)/usr/sbin/{aprx,aprx-stat} \
	  $(1)/usr/sbin/
endef

$(eval $(call BuildPackage,aprx))
