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
PKG_VERSION:=2.3
PKG_RELEASE:=112

PKG_LICENSE:=GPL-3.0

include $(INCLUDE_DIR)/package.mk

define Package/A-default-settings
  SECTION:=luci
  CATEGORY:=LuCI
  TITLE:=LuCI support for Default Settings
  DEPENDS:=+luci
  PKGARCH:=all
endef

define Build/Prepare
	chmod -R +x ./files/usr/share target/*/{*,}/base-files/{etc/init.d,usr/bin} >/dev/null || true
endef

define Build/Compile
endef

define Package/A-default-settings/install
	$(CP) ./files/* $(1)/
endef

$(eval $(call BuildPackage,A-default-settings))
