#
# Copyright (C) 2021 Lean <coolsnowwolf@gmail.com>
#
# Copyright (C) 2021 ImmortalWrt
# <https://immortalwrt.org>
#
# This is free software, licensed under the GNU General Public License v2.
# See /LICENSE for more information.
#

include $(TOPDIR)/rules.mk

PKG_NAME:=A-default-settings
PKG_VERSION:=1.1
PKG_RELEASE:=112

PKG_LICENSE:=GPL-3.0

include $(INCLUDE_DIR)/package.mk

define Package/A-default-settings
  SECTION:=luci
  CATEGORY:=LuCI
  TITLE:=LuCI support for Default Settings
  DEPENDS:=+luci +luci-base +openssl-util +@LUCI_LANG_zh_Hans
  PKGARCH:=all
endef

define Package/A-default-settings/description
	LuCI Chinese, status links, system default config.
endef

define Build/Compile
endef

define Package/A-default-settings/install
	$(CP) ./noodles/* $(1)/
	$(INSTALL_DIR) $(1)/etc/uci-defaults
	$(INSTALL_BIN) ./files/zzz-default-settings $(1)/etc/uci-defaults/99-default-settings
	$(INSTALL_DIR) $(1)/usr/lib/lua/luci/i18n
	po2lmo ./i18n/default.zh_Hans.po $(1)/usr/lib/lua/luci/i18n/default.zh-cn.lmo
endef

$(eval $(call BuildPackage,A-default-settings))
