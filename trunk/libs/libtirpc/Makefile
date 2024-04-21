include $(ROOTDIR)/rules.mk

PKG_NAME:=libtirpc
PKG_VERSION:=1.3.4

PKG_SOURCE:=$(PKG_NAME)-$(PKG_VERSION).tar.bz2
PKG_SOURCE_URL:=@SF/$(PKG_NAME)
PKG_HASH:=1e0b0c7231c5fa122e06c0609a76723664d068b0dba3b8219b63e6340b347860

PKG_FIXUP:=autoreconf

include $(INCLUDE_DIR)/package.mk

CONFIGURE_ARGS += \
	--enable-shared \
	--disable-static \
	--disable-gssapi

$(eval $(call BuildPackage,libtirpc))

romfs:
	$(INSTALL_DIR) $(ROMFSDIR)/lib
	$(CP) $(PKG_INSTALL_DIR)/lib/libtirpc.so* $(ROMFSDIR)/lib/
	$(INSTALL_DIR) $(ROMFSDIR)/etc_ro
	$(INSTALL_DATA) $(PKG_INSTALL_DIR)/etc/netconfig $(ROMFSDIR)/etc_ro/netconfig
