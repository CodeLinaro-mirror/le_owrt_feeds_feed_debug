# WARNING: Automatically generated file using BAF (Build system Agnostic File) tooling
# WARNING: You should contribute changes to https://gitlab.com/prpl-foundation/components/utilities/debug-information/-/blob/main/baf.yml instead
include $(TOPDIR)/rules.mk

PKG_NAME:=debug-information
PKG_VERSION:=sah-next-4.1_v0.1.2
SHORT_DESCRIPTION:=Scripts to provide debug Information for a running system

PKG_SOURCE:=debug-information-sah-next-4.1_v0.1.2.tar.gz
PKG_SOURCE_URL:=https://gitlab.com/prpl-foundation/components/utilities/debug-information/-/archive/sah-next-4.1_v0.1.2
PKG_HASH:=eedde7cb3d8511222177ba2c257fcbe63710ac2df663a56122f35a8b6d5e6124
PKG_BUILD_DIR:=$(BUILD_DIR)/debug-information-sah-next-4.1_v0.1.2
PKG_MAINTAINER:=Soft At Home <support.opensource@softathome.com>
PKG_LICENSE:=BSD-2-Clause-Patent
PKG_LICENSE_FILES:=LICENSE

COMPONENT:=debug-information

PKG_RELEASE:=1

define SAHInit/Install
	install -d $(1)/etc/rc.d/
	ln -sfr $(1)/etc/init.d/boot_measure $(1)/etc/rc.d/S12boot_measure
	ln -sfr $(1)/etc/init.d/boot_measure $(1)/etc/rc.d/K12boot_measure
endef

include $(INCLUDE_DIR)/package.mk

define Package/$(PKG_NAME)
  CATEGORY:=prpl Foundation
  SUBMENU:=Ambiorix
  TITLE:=$(SHORT_DESCRIPTION)
  URL:=https://gitlab.com/prpl-foundation/components/utilities/debug-information
  DEPENDS += +procps-ng
  DEPENDS += +procps-ng-pmap
  DEPENDS += +procps-ng-ps
  DEPENDS += +lua-amx
  DEPENDS += +lua5.3
  MENU:=1
endef

define Package/$(PKG_NAME)/description
	Scripts to provide debug Information for a running system
endef

define Build/Compile
	$(call Build/Compile/Default, STAGINGDIR=$(STAGING_DIR) CONFIGDIR=$(STAGING_DIR) PKG_CONFIG_PATH=$(STAGING_DIR)/usr/lib/pkgconfig LIBDIR=/usr/lib INSTALL_LIB_DIR=/lib INSTALL_BIN_DIR=/bin RAW_VERSION=$(PKG_VERSION) HARDCO_HAL_DIR=$(STAGING_DIR)/usr/include PKG_CONFIG=$(PKG_CONFIG) CONFIG_SAH_AMX_DEBUG_INFORMATION_LUA_VERSION=$(CONFIG_SAH_AMX_DEBUG_INFORMATION_LUA_VERSION) CONFIG_GATEWAY=$(CONFIG_GATEWAY) CONFIG_ACCESSPOINT=$(CONFIG_ACCESSPOINT))
endef

define Build/Install
	$(call Build/Install/Default, install INSTALL=install D=$(PKG_INSTALL_DIR) DEST=$(PKG_INSTALL_DIR) STAGINGDIR=$(STAGING_DIR) CONFIGDIR=$(STAGING_DIR) PV=$(PKG_VERSION) PKG_CONFIG_LIBDIR=$(STAGING_DIR)/usr/lib/pkgconfig LIBDIR=/usr/lib INSTALL_LIB_DIR=/lib INSTALL_BIN_DIR=/bin RAW_VERSION=$(PKG_VERSION) HARDCO_HAL_DIR=$(STAGING_DIR)/usr/include PKG_CONFIG=$(PKG_CONFIG) CONFIG_SAH_AMX_DEBUG_INFORMATION_LUA_VERSION=$(CONFIG_SAH_AMX_DEBUG_INFORMATION_LUA_VERSION) CONFIG_GATEWAY=$(CONFIG_GATEWAY) CONFIG_ACCESSPOINT=$(CONFIG_ACCESSPOINT))

	$(call SAHInit/Install,$(PKG_INSTALL_DIR))
endef

define Build/InstallDev
	$(call Build/Install/Default, install INSTALL=install D=$(STAGING_DIR) DEST=$(STAGING_DIR) STAGINGDIR=$(STAGING_DIR) CONFIGDIR=$(STAGING_DIR) PV=$(PKG_VERSION) PKG_CONFIG_LIBDIR=$(STAGING_DIR)/usr/lib/pkgconfig LIBDIR=/usr/lib INSTALL_LIB_DIR=/lib INSTALL_BIN_DIR=/bin RAW_VERSION=$(PKG_VERSION) HARDCO_HAL_DIR=$(STAGING_DIR)/usr/include PKG_CONFIG=$(PKG_CONFIG) CONFIG_SAH_AMX_DEBUG_INFORMATION_LUA_VERSION=$(CONFIG_SAH_AMX_DEBUG_INFORMATION_LUA_VERSION) CONFIG_GATEWAY=$(CONFIG_GATEWAY) CONFIG_ACCESSPOINT=$(CONFIG_ACCESSPOINT))
	$(call SAHInit/Install,$(STAGING_DIR))
endef

define Package/$(PKG_NAME)/install
	$(CP) $(PKG_INSTALL_DIR)/* $(1)/
	if [ -d ./files ]; then \
		$(CP) ./files/* $(1)/; \
	fi
	find $(1) -name *.a -exec rm {} +;
	find $(1) -name *.h -exec rm {} +;
	find $(1) -name *.pc -exec rm {} +;
endef

define Package/$(PKG_NAME)/config
	source "$(SOURCE)/Config.in"
endef

$(eval $(call BuildPackage,$(PKG_NAME)))
