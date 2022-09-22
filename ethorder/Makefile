include $(TOPDIR)/rules.mk
 
PKG_NAME:=ethorder
PKG_VERSION:=1.0.0
PKG_RELEASE:=1
 
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

define Package/ethconfig/conffiles
/etc/config/ethorder
endef

define Build/Compile
endef

define Build/Configure
endef

define Package/ethorder/install
	$(INSTALL_DIR) $(1)/etc/init.d
	$(INSTALL_BIN) ./files/etc/init.d/ethorder \
		$(1)/etc/init.d/ethorder

	$(INSTALL_DIR) $(1)/etc/config
	$(INSTALL_CONF) ./files/etc/config/ethorder \
		$(1)/etc/config/ethorder
	
	$(INSTALL_DIR) $(1)/usr/share/ethorder
	echo "$(PKG_VERSION)-$(PKG_RELEASE)" > $(1)/usr/share/ethorder/version
endef

define Package/ethorder/postinst
#!/bin/sh
if [ -z "$${IPKG_INSTROOT}" ]; then
	/etc/init.d/ethorder enabled
fi
exit 0
endef

define Package/ethorder/prerm
#!/bin/sh
if [ -n "$${IPKG_INSTROOT}" ]; then
	/etc/init.d/ethorder disable
fi
exit 0
endef

$(eval $(call BuildPackage,ethorder))
