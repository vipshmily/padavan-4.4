include $(ROOTDIR)/rules.mk

PKG_NAME:=sqlite
PKG_VERSION:=3460000

PKG_SOURCE:=$(PKG_NAME)-autoconf-$(PKG_VERSION).tar.gz
PKG_SOURCE_URL:=https://www.sqlite.org/2024/
PKG_HASH:=6f8e6a7b335273748816f9b3b62bbdc372a889de8782d7f048c653a447417a7d

PKG_BUILD_DIR:=$(BUILD_DIR)/$(PKG_NAME)-autoconf-$(PKG_VERSION)

include $(INCLUDE_DIR)/package.mk

CONFIGURE_ARGS += \
	$(if $(LIBS_BUILD_SHARED),--disable-static,--enable-static) \
	$(if $(LIBS_BUILD_SHARED),--enable-shared,--disable-shared) \
	--disable-readline \
	--disable-dynamic-extensions \
	--disable-fts3 \
	--disable-fts4 \
	--disable-fts5 \
	--disable-json1 \
	--disable-rtree \
	--disable-session \
	--disable-debug \
	--disable-static-shell

$(eval $(call BuildPackage,sqlite))

romfs:
	$(INSTALL_DIR) $(ROMFSDIR)/lib
	$(CP) $(PKG_INSTALL_DIR)/lib/libsqlite3.so* $(ROMFSDIR)/lib/
