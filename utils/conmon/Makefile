include $(TOPDIR)/rules.mk

PKG_NAME:=conmon
PKG_VERSION:=2.0.30
PKG_RELEASE:=$(AUTORELEASE)

PKG_SOURCE:=$(PKG_NAME)-$(PKG_VERSION).tar.gz
PKG_SOURCE_URL:=https://github.com/containers/$(PKG_NAME)/archive/v$(PKG_VERSION)
PKG_HASH:=4b0a98fbe8a63c42f60edac25c19aa6606caa7b1e4fe7846fc7f7de0b566ba25

PKG_MAINTAINER:=Oskari Rauta <oskari.rauta@gmail.com>
PKG_LICENSE:=Apache-2.0
PKG_LICENSE_FILES:=LICENSE

PKG_BUILD_DEPENDS:=golang/host libseccomp

include $(INCLUDE_DIR)/package.mk
include $(INCLUDE_DIR)/nls.mk
include $(INCLUDE_DIR)/meson.mk

define Package/conmon
  SECTION:=utils
  CATEGORY:=Utilities
  TITLE:=Podman conmon
  URL:=https://podman.io
  DEPENDS:=@!arc +glib2 $(INTL_DEPENDS) $(ICONV_DEPENDS)
endef

define Package/conmon/description
  An OCI container runtime monitor.

  Conmon is a monitoring program and communication tool between
  a container manager (like Podman or CRI-O) and an OCI runtime
  (like runc or crun) for a single container.
endef

define Package/conmon/install
	$(INSTALL_DIR) $(1)/usr/bin
	$(INSTALL_BIN) $(PKG_INSTALL_DIR)/usr/libexec/podman/conmon $(1)/usr/bin
endef

$(eval $(call BuildPackage,conmon))
