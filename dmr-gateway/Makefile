include $(TOPDIR)/rules.mk

PKG_NAME:=dmrgateway
PKG_RELEASE:=1

PKG_SOURCE_PROTO:=git
PKG_SOURCE_URL:=https://github.com/g4klx/DMRGateway.git
PKG_SOURCE_VERSION:=master
PKG_MIRROR_HASH:=skip

PKG_LICENSE:=GPL-2.0
PKG_LICENSE_FILES:=COPYING

include $(INCLUDE_DIR)/package.mk

define Package/dmrgateway
  SECTION:=utils
  CATEGORY:=Utilities
  TITLE:=Multi-network DMR Gateway for MMDVM
  URL:=https://github.com/g4klx/DMRGateway
  DEPENDS:=+libstdcpp
endef

define Package/dmrgateway/description
  DMRGateway allows connection to multiple DMR networks from one MMDVM system.
endef

define Build/Compile
	$(MAKE) -C $(PKG_BUILD_DIR) \
		CXX="$(TARGET_CXX)" \
		CXXFLAGS="$(TARGET_CXXFLAGS)" \
		LDFLAGS="$(TARGET_LDFLAGS)"
endef

define Package/dmrgateway/install
	$(INSTALL_DIR) $(1)/usr/bin
	$(INSTALL_BIN) $(PKG_BUILD_DIR)/DMRGateway $(1)/usr/bin/
endef

$(eval $(call BuildPackage,dmrgateway))
