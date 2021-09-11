#
# Copyright (C) 2007-2015 OpenWrt.org
#
# This is free software, licensed under the GNU General Public License v2.
# See /COPYING for more information.
#

include $(TOPDIR)/rules.mk

PKG_NAME:=bash-completion
PKG_VERSION:=2.11
PKG_RELEASE:=1

PKG_SOURCE:=$(PKG_NAME)-$(PKG_VERSION).tar.xz
PKG_SOURCE_URL:=https://github.com/scop/bash-completion/releases/download/$(PKG_VERSION)/
PKG_HASH:=73a8894bad94dee83ab468fa09f628daffd567e8bef1a24277f1e9a0daf911ac
PKG_MAINTAINER:=acooler15 <acooler15@foxmail.com>
PKG_LICENSE:=GPL-2.0-or-later
PKG_LICENSE_FILES:=COPYING

PKG_INSTALL:=1
PKG_BUILD_PARALLEL:=1

include $(INCLUDE_DIR)/package.mk

define Package/bash-completion/conffiles
/etc/bash_completion.d/
endef

define Package/bash-completion
	SECTION:=utils
	CATEGORY:=Utilities
	SUBMENU:=Shells
	TITLE:=Programmable completion for the Bash shell
	DEPENDS:=+bash +procps-ng-ps
	URL:=https://github.com/scop/bash-completion
endef

define Package/bash-completion/description
	bash-completion is a collection of command line command completions for the Bash shell, 
	collection of helper functions to assist in creating new completions, 
	and set of facilities for loading completions automatically on demand, as well as installing them.
endef

define Package/bash-completion/install
	$(INSTALL_DIR) $(1)/etc/profile.d
	$(CP) $(PKG_INSTALL_DIR)/etc/profile.d/* $(1)/etc/profile.d/
	$(INSTALL_DIR) $(1)/usr/share/bash-completion
	$(CP) $(PKG_INSTALL_DIR)/usr/share/bash-completion/* $(1)/usr/share/bash-completion/
	$(INSTALL_DIR) $(1)/etc/bash_completion.d
endef

$(eval $(call BuildPackage,bash-completion))
