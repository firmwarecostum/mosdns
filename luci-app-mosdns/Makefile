include $(TOPDIR)/rules.mk

PKG_NAME:=luci-app-mosdns
PKG_VERSION:=909
PKG_RELEASE:=1
PKG_LICENSE:=GPL-2.0

PKG_MAINTAINER:=
#PKG_BUILD_DEPENDS:=python-jupyter-packaging/host python-hatch/host python-jupyter-server/host python-jupyterlab/host python-jupyterlab-server/host python-jupyter-client/host python-hatch-nodejs-version/host
#PKG_BUILD_DEPENDS:=python3/host python-build/host python-installer/host python-hatchling/host python-hatch-vcs/host python-zstandard/host python-httpx/host python-click/host python-userpath/host python-shellingham/host python-rich/host python-tomlkit/host python-virtualenv/host python-tomli-w/host python-jupyter-packaging/host python-platformdirs/host python-keyring/host python-hyperlink/host python-pexpect/host
PKG_BUILD_DIR:=$(BUILD_DIR)/$(PKG_NAME)
PKG_BUILD_PARALLEL:=1

include $(INCLUDE_DIR)/package.mk

define Package/luci-app-mosdns
  SECTION:=net
  CATEGORY:=Network
  #DEPENDS:=perl perl-html-tagset perl-net-dns perl-ack perl-html-tree perl-net-http perl-authen-sasl perl-http-cookies perl-net-telnet perl-authen-sasl-xs perl-http-daemon perl-parse-recdescent perl-cgi perl-http-date perl-parse-yapp perl-compress-bzip2 perl-http-message perl-sub-uplevel perl-dbi perl-http-negotiate perl-test-harness perl-device-serialport perl-http-server-simple perl-test-warn perl-device-usb perl-inline perl-text-csv_xs perl-encode-locale perl-inline-c perl-try-tiny perl-file-listing perl-io-html perl-uri perl-file-next perl-lockfile-simple perl-www perl-file-rsyncp perl-lwp-mediatypes perl-www-curl perl-file-sharedir-install perl-mail-spamassassin perl-www-mechanize perl-html-form perl-netaddr-ip perl-www-robotrules perl-html-parser perl-net-cidr-lite perl-xml-parser
  #DEPENDS:=perl perlbase-anydbm-file perlbase-app perlbase-archive perlbase-attribute perlbase-attributes perlbase-autodie perlbase-autoloader perlbase-autosplit perlbase-autouse perlbase-b perlbase-base perlbase-benchmark perlbase-bigint perlbase-bignum perlbase-blib perlbase-bytes perlbase-charnames perlbase-class perlbase-compress perlbase-config perlbase-cpan perlbase-cwd perlbase-data perlbase-db perlbase-db-file perlbase-dbm-filter perlbase-devel perlbase-diagnostics perlbase-digest perlbase-dirhandle perlbase-dumpvalue perlbase-dumpvar perlbase-dynaloader perlbase-encode perlbase-encoding perlbase-english perlbase-env perlbase-errno perlbase-essential perlbase-experimental perlbase-extutils perlbase-fatal perlbase-fcntl perlbase-feature perlbase-fields perlbase-file perlbase-filecache perlbase-filehandle perlbase-filetest perlbase-filter perlbase-findbin perlbase-gdbm-file perlbase-getopt perlbase-hash perlbase-http-tiny perlbase-i18n perlbase-if perlbase-integer perlbase-io perlbase-ipc perlbase-json-pp perlbase-less perlbase-list perlbase-locale perlbase-math perlbase-memoize perlbase-meta-notation perlbase-mime perlbase-module perlbase-mro perlbase-net perlbase-next perlbase-o perlbase-opcode perlbase-open perlbase-ops perlbase-ostype perlbase-params perlbase-perl5db perlbase-perlio perlbase-pod perlbase-posix perlbase-re perlbase-safe perlbase-scalar perlbase-sdbm-file perlbase-search perlbase-selectsaver perlbase-selfloader perlbase-sigtrap perlbase-socket perlbase-sort perlbase-storable perlbase-symbol perlbase-sys perlbase-tap perlbase-term perlbase-test perlbase-text perlbase-thread perlbase-threads perlbase-tie perlbase-time perlbase-unicode perlbase-unicore perlbase-universal perlbase-user perlbase-utf8 perlbase-version perlbase-xsloader
  #DEPENDS:=+mumble +alsa-lib +celt +libavahi-compat-libdnssd +libsndfile +libopenssl +libcap +libx11 +libxi +qt5-Concurrent +qt5-Core +qt5-DBus +qt5-Gui +qt5-Network +qt5-PrintSupport +qt5-Sql +qt5-Test +qt5-Widgets +qt5-Xml +poco-all +protobuf +librnnoise +libspeex +libspeexdsp +libopus
  DEPENDS:=python3-aiooui
  #DEPENDS:=+python3-aiodhcpwatcher +python3-aiodiscover +python3-aiodns +python3-aiohasupervisor +python3-aiohttp-asyncmdnsresolver +python3-aiohttp-fast-zlib +python3-aiohttp +python3-aiohttp-cors +python3-aiousbwatcher +python3-aiozoneinfo +python3-annotatedyaml +python3-astral +python3-async-interrupt +python3-async-upnp-client +python3-atomicwrites-homeassistant +python3-attrs +python3-audioop-lts +python3-av +python3-awesomeversion +python3-bcrypt +python3-bleak-retry-connector +python3-bleak +python3-bluetooth-adapters +python3-bluetooth-auto-recovery +python3-bluetooth-data-tools +python3-cached-ipaddress +python3-certifi +python3-ciso8601 +python3-cronsim +python3-cryptography +python3-dbus-fast +python3-file-read-backwards +python3-fnv-hash-fast +python3-go2rtc-client +python3-ha-ffmpeg +python3-habluetooth +python3-hass-nabucasa +python3-hassil +python3-home-assistant-bluetooth +python3-home-assistant-frontend +python3-home-assistant-intents +python3-httpx +python3-ifaddr +python3-jinja2 +python3-lru-dict +python3-mutagen +python3-orjson +python3-packaging +python3-paho-mqtt +python3-pillow +python3-propcache +python3-psutil-home-assistant +python3-pyjwt +python3-pymicro-vad +python3-pynacl +python3-pyopenssl +python3-pyserial +python3-pyspeex-noise +python3-slugify +python3-pyturbojpeg +python3-yaml +python3-requests +python3-securetar +python3-sqlalchemy +python3-standard-aifc +python3-standard-telnetlib +python3-typing-extensions +python3-ulid-transform +python3-urllib3 +python3-uv +python3-voluptuous-openapi +python3-voluptuous-serialize +python3-voluptuous +python3-webrtc-models +python3-yarl +python3-zeroconf +python3-cryptodome +python3-httplib2 +python3-grpcio +python3-grpcio-status +python3-grpcio-reflection +python3-btlewrap +python3-anyio +python3-h11 +python3-httpcore +python3-hyperframe +python3-numpy +python3-pandas +python3-multidict +python3-backoff +python3-pydantic +python3-mashumaro +python3-pubnub +python3-iso4217 +python3-protobuf +python3-faust-cchardet +python3-websockets +python3-getmac +python3-charset-normalizer +python3-dacite +python3-chacha20poly1305-reuseable +python3-pycountry +python3-scapy +python3-tuf +python3-tenacity +python3-async-timeout +python3-aiofiles +python3-multidict +python3-rpds-py +python3-num2words +python3-pymodbus +python3-gql +python3-pytest-rerunfailures
  #DEPENDS:=+python3-pyserial +python3-protobuf +python3-tabulate +python3-requests +python3-yaml +python3-pypubsub +python3-bleak +python3-packaging +python3-argcomplete +python3-pyqrcode +python3-dotmap +python3-print-color +python3-dash +python3-pytap2 +python3-dash-bootstrap-components +python3-pandas +python3-pandas-stubs +python3-wcwidth
  TITLE:=Tools Inject xderm-mini
endef

define Package/luci-app-mosdns/description
 xderm-mini ssh v2ray trojan
endef

define Build/Prepare
endef

define Build/Configure
endef

define Build/Compile
endef

define Package/luci-app-mosdns/install
	#$(INSTALL_DIR) $(1)/usr/lib
	#$(CP) $(HOST_PYTHON3_PKG_DIR)/numpy/_core/lib/libnpymath.a $(1)/usr/lib/
endef

$(eval $(call BuildPackage,luci-app-mosdns))
