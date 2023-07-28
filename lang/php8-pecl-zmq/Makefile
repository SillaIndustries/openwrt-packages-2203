# This is free software, licensed under the GNU General Public License v2.
# See /LICENSE for more information.

include $(TOPDIR)/rules.mk

PECL_NAME:=zmq
PECL_LONGNAME:=PHP extension for ZeroMQ software library
PKG_NAME:=php8-pecl-zmq
PKG_VERSION:=1.1.2
PKG_RELEASE:=1

PKG_SOURCE:=$(PKG_NAME)-$(PKG_VERSION).tar.gz
PKG_SOURCE_PROTO:=git
PKG_SOURCE_URL:=https://github.com/SillaIndustries/php-zmq.git
PKG_SOURCE_VERSION:=openwrt-build
PKG_HASH:=dc63d8a44aeaca0cf1c88f1f6d43a04b973d5572

define Package/php8-pecl-zmq
    TITLE:=PHP ZeroMQ Extension
endef

define Package/php8-pecl-zmq/description
    PHP ZeroMQ Extension description
endef


PKG_MAINTAINER:=Michael Heimpold <mhei@heimpold.de>

PKG_LICENSE:=BSD-3-Clause
PKG_LICENSE_FILES:=LICENSE

PKG_BUILD_DIR:=$(BUILD_DIR)/pecl-php8/php8-pecl-zmq-$(PKG_VERSION)
PKG_BUILD_PARALLEL:=1

include $(INCLUDE_DIR)/package.mk
include $(INCLUDE_DIR)/nls.mk
include ../php8/pecl.mk

PKG_FIXUP:=patch-libtool

CONFIGURE_ARGS+= \
        --with-zmq=yes \
        --with-czmq=no

$(eval $(call PHP8PECLPackage,$(PECL_NAME),$(PECL_LONGNAME),+libzmq))
$(eval $(call BuildPackage,$(PKG_NAME)))
