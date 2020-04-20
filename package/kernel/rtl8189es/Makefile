include $(TOPDIR)/rules.mk

PKG_NAME:=rtl8189es
PKG_RELEASE=1

PKG_LICENSE:=GPLv2
PKG_LICENSE_FILES:=

PKG_SOURCE_URL:=https://github.com/jwrdegoede/rtl8189ES_linux.git
PKG_SOURCE_PROTO:=git
PKG_SOURCE_DATE:=2020-04-05
PKG_SOURCE_VERSION:=master
#PKG_SOURCE_VERSION:=8c3acf92759861e82b552b1f0ef1a26b26391071
#PKG_MIRROR_HASH:=7a1da26a39c3d1ba8ef30b74fb3ef3cfdb672c45f1dd466c057a6fb68beb0540
CRLF_WORKAROUND:=1

PKG_MAINTAINER:=Hauke Mehrtens <hauke@hauke-m.de>

STAMP_CONFIGURED_DEPENDS := $(STAGING_DIR)/usr/include/mac80211-backport/backport/autoconf.h

include $(INCLUDE_DIR)/kernel.mk
include $(INCLUDE_DIR)/package.mk

define KernelPackage/rtl8189es
  SUBMENU:=Wireless Drivers
  TITLE:=Realtek RTL8189ES / RTL8189ETV SDIO WiFi
  DEPENDS:=+kmod-cfg80211 +kmod-mmc +@DRIVER_11N_SUPPORT 
  FILES:=$(PKG_BUILD_DIR)/8189es.ko
  AUTOLOAD:=$(call AutoLoad,50,cfg80211 8189es)
endef

NOSTDINC_FLAGS = \
	-I$(STAGING_DIR)/usr/include/mac80211-backport/uapi \
	-I$(STAGING_DIR)/usr/include/mac80211-backport \
	-I$(STAGING_DIR)/usr/include/mac80211/uapi \
	-I$(STAGING_DIR)/usr/include/mac80211 \
	-include backport/autoconf.h \
	-include backport/backport.h

define Build/Compile
	+$(MAKE) $(PKG_JOBS) -C $(LINUX_DIR) \
		ARCH=$(LINUX_KARCH) \
		CROSS_COMPILE=$(TARGET_CROSS) \
		SUBDIRS="$(PKG_BUILD_DIR)" \
		NOSTDINC_FLAGS="$(NOSTDINC_FLAGS)" \
		CONFIG_RTL8189ES=m \
		modules
endef

$(eval $(call KernelPackage,rtl8189es))
