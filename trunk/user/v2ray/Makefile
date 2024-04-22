include $(ROOTDIR)/rules.mk

PKG_NAME:=v2ray
PKG_VERSION:=5.16.1

PKG_SOURCE:=$(PKG_NAME)-$(PKG_VERSION).tar.gz
PKG_SOURCE_URL:=https://codeload.github.com/v2fly/v2ray-core/tar.gz/v$(PKG_VERSION)?
PKG_HASH:=e5d61b97168ebdf6da3d672ab40abe5b22951d46997072ca1ee497a3aa47ba05

PKG_BUILD_DIR:=$(BUILD_DIR)/v2ray-core-$(PKG_VERSION)

include $(INCLUDE_DIR)/package.mk

define Build/Configure
endef

define Build/Compile
	(cd $(PKG_BUILD_DIR); \
		GOOS=linux GOARCH=mipsle CGO_ENABLED=0 \
		go build -v -o v2ray \
		-trimpath -ldflags "-s -w -buildid=" \
		./main; \
	)
endef

$(eval $(call BuildPackage,v2ray))

romfs:
	$(INSTALL_DIR) $(ROMFSDIR)/usr/bin
	$(INSTALL_BIN) $(PKG_BUILD_DIR)/v2ray $(ROMFSDIR)/usr/bin/v2ray
