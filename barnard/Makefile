include $(TOPDIR)/rules.mk

PKG_NAME:=barnard
PKG_VERSION:=v0.0.0
PKG_RELEASE:=1

PKG_SOURCE_URL:=https://github.com/layeh/barnard.git
PKG_SOURCE_PROTO:=git
PKG_SOURCE_VERSION:=ae15ac70546876be99b891e33cf1bb5ed09f1680
PKG_MIRROR_HASH:=skip

PKG_MAINTAINER:=Esa Aprilia Salsabila <esaapriliasalsabila@gmail.com>
PKG_LICENSE:=GPL-2.0 license
PKG_LICENSE_FILES:=LICENSE

PKG_BUILD_DEPENDS:=golang/host
PKG_BUILD_PARALLEL:=1
PKG_USE_MIPS16:=0
PKG_BUILD_FLAGS:=no-mips16

GO_PKG:=layeh.com/barnard

include $(INCLUDE_DIR)/package.mk
include $(TOPDIR)/feeds/packages/lang/golang/golang-package.mk

define Package/barnard
  SECTION:=net
  CATEGORY:=Network
  TITLE:=barnard is a terminal-based client for the Mumble voice chat software
  URL:=https://github.com/layeh/barnard
  DEPENDS:=$(GO_ARCH_DEPENDS) +openal-soft +libopus +libopenssl
endef

define Package/barnard/description
  barnard is a terminal-based client for the Mumble voice chat software
endef

GO_PKG_BUILD_VARS += GO111MODULE=auto

define Package/barnard/install
	$(call GoPackage/Package/Install/Bin,$(PKG_INSTALL_DIR))
	$(INSTALL_DIR) $(1)/usr/bin/
	$(INSTALL_BIN) $(PKG_INSTALL_DIR)/usr/bin/barnard $(1)/usr/bin/
endef

$(eval $(call BuildPackage,barnard))
