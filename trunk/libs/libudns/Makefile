include $(ROOTDIR)/rules.mk

PKG_NAME:=udns
PKG_VERSION:=0.5

PKG_SOURCE:=$(PKG_NAME)-$(PKG_VERSION).tar.gz
PKG_SOURCE_URL:=http://www.corpit.ru/mjt/udns/
PKG_HASH:=035bfc12e3819d0aba8f40ee8220a974b7e9b29c3259d310970cc4b2d1c203c0

PKG_FIXUP:=autoreconf

include $(INCLUDE_DIR)/package.mk

$(eval $(call BuildPackage,udns))

romfs:
