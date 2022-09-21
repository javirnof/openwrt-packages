include $(TOPDIR)/rules.mk
 
PKG_NAME:=ethorder
PKG_VERSION:=1.0.0
PKG_RELEASE:=1
 
PKG_BUILD_DIR:=$(BUILD_DIR)/ethorder-$(PKG_VERSION)
PKG_SOURCE:=ethorder-$(PKG_VERSION).tar.gz
PKG_SOURCE_URL:=https://github.com/javirnof/ethorder/archive/refs/tags/1.0.0.tar.gz
PKG_HASH:=349fb8ed73a06fe0ce240a5436b0fdaa
 
include $(INCLUDE_DIR)/package.mk
 
define Package/ethorder
  SECTION:=base
  CATEGORY:=Network
  TITLE:=Ethernet order by mac
  URL:=https://github.com/javirnof/ethorder
endef
 
define Package/ethorder/description
	Ethernet order by mac. Define static asignation for eth interfaces based on macs
endef
 
define Package/ethorder/install
        $(INSTALL_DIR) $(1)/etc/init.d
        $(INSTALL_BIN) $(PKG_BUILD_DIR)/ethorder-$(PKG_VERSION)/ethorder $(1)/etc/init.d/ethorder
endef
 
$(eval $(call BuildPackage,ethorder))