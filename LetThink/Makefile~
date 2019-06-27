include $(TOPDIR)/rules.mk

PKG_NAME:=LetThink
PKG_RELEASE:=1
PKG_BUILD_DIR:=$(BUILD_DIR)/$(PKG_NAME)

include $(INCLUDE_DIR)/package.mk

define Package/LetThink
    SECTION:=utils
    CATEGORY:=Utilities
    TITLE:=LetThink -- prints a snarky message
endef

define Package/LetThink/description
    It's my first package demo.
endef

define Build/Prepare
	echo "Here is Package/Prepare"
	mkdir -p $(PKG_BUILD_DIR)
	$(CP) -rf ./src/* $(PKG_BUILD_DIR)/
endef
define Build/Compile
	$(TARGET_CC) $(TARGET_CFLAGS) -fprofile-generate -o $(PKG_BUILD_DIR)/LetThink $(PKG_BUILD_DIR)/source/*.c -I$(PKG_BUILD_DIR)/include/ 
endef
define Package/LetThink/install
	echo "Here is Package/install"
	$(INSTALL_DIR) $(1)/bin
	$(INSTALL_BIN) $(PKG_BUILD_DIR)/LetThink $(1)/bin/
endef
    
$(eval $(call BuildPackage,LetThink))
