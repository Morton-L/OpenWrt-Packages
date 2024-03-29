#
# This is free software, licensed under the GNU General Public License v2.
# See /LICENSE for more information.
#

include $(TOPDIR)/rules.mk

PKG_NAME:=expat
PKG_VERSION:=2.2.10
PKG_RELEASE:=2

PKG_SOURCE:=$(PKG_NAME)-$(PKG_VERSION)-RENAMED-VULNERABLE-PLEASE-USE-2.4.1-INSTEAD.tar.xz
PKG_SOURCE_URL:=@SF/expat
PKG_HASH:=5dfe538f8b5b63f03e98edac520d7d9a6a4d22e482e5c96d4d06fcc5485c25f2

PKG_MAINTAINER:=Ted Hess <thess@kitschensync.net>
PKG_LICENSE:=MIT
PKG_LICENSE_FILES:=COPYING
PKG_CPE_ID:=cpe:/a:libexpat:expat

PKG_FIXUP:=autoreconf
PKG_INSTALL:=1
PKG_BUILD_PARALLEL:=1

include $(INCLUDE_DIR)/host-build.mk
include $(INCLUDE_DIR)/package.mk

define Package/libexpat
  SECTION:=libs
  CATEGORY:=Libraries
  TITLE:=An XML parsing library
  URL:=https://libexpat.github.io/
endef

define Package/libexpat/description
 A fast, non-validating, stream-oriented XML parsing library.
endef

TARGET_CFLAGS += $(FPIC)

CONFIGURE_ARGS += \
	--enable-shared \
	--enable-static \
	--without-docbook

HOST_CONFIGURE_ARGS += \
	--without-docbook

define Host/Install
	$(MAKE) -C $(HOST_BUILD_DIR) install
endef

define Build/InstallDev
	$(INSTALL_DIR) $(1)/usr/include
	$(CP) $(PKG_INSTALL_DIR)/usr/include/expat{,_external}.h $(1)/usr/include/

	$(INSTALL_DIR) $(1)/usr/lib/pkgconfig
	$(INSTALL_DATA) $(PKG_INSTALL_DIR)/usr/lib/pkgconfig/expat.pc $(1)/usr/lib/pkgconfig/

	$(INSTALL_DIR) $(1)/usr/lib
	$(CP) $(PKG_INSTALL_DIR)/usr/lib/libexpat.{a,so*} $(1)/usr/lib/
endef

define Package/libexpat/install
	$(INSTALL_DIR) $(1)/usr/lib
	$(CP) $(PKG_INSTALL_DIR)/usr/lib/libexpat.so.* $(1)/usr/lib/
endef

$(eval $(call HostBuild))
$(eval $(call BuildPackage,libexpat))
