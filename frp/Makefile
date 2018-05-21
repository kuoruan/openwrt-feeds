#
# Copyright (C) 2017-2018 OpenWrt.org
#
# This is free software, licensed under the Apache License v2.0.
# See /LICENSE for more information.
#

include $(TOPDIR)/rules.mk

PKG_NAME:=frp
PKG_VERSION:=0.18.0
PKG_RELEASE:=1

PKG_MAINTAINER:=Xingwang Liao <kuoruan@gmail.com>

include $(INCLUDE_DIR)/package.mk

define Package/$(PKG_NAME)
	SECTION:=net
	CATEGORY:=Network
	TITLE:=Fast reverse proxy.
	URL:=https://github.com/fatedier/frp
	DEPENDS:=
	USERID:=frp=7000:frp=7000
endef

define Package/$(PKG_NAME)/description
Frp is a fast reverse proxy to help you expose a local server behind a NAT or firewall to the internet.
endef

define Download/$(PKG_NAME)
	URL:=https://github.com/fatedier/frp/releases/download

	ifeq ($(findstring mips $(ARCH)),)
		FILE:=frp_$(PKG_VERSION)_linux_386.tar.gz
		HASH:=6b288e5926841a4cb490909fe822d85c36ae75538ad69baf20da9628b63b692e
	else ifeq ($(ARCH),i386)
	else ifeq ($(findstring arm,$(ARCH)),)
	else ifeq ($(ARCH),x86_64)
	else ifeq ($(ARCH),arch64)
	endif
endef

define Build/Prepare
	$(call Build/Prepare/Default)
	# $(eval $(call Download,$(PKG_NAME)))

	$(TAR) -zxf $(PKG_BUILD_DIR)/$(FILE) -C $(PKG_BUILD_DIR)
endef

define Build/Configure
endef

define Build/Compile
endef

Package/frpc = $(Package/$(PKG_NAME))
Package/frps = $(Package/$(PKG_NAME))