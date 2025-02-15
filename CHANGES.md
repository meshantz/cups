CHANGES - OpenPrinting CUPS 2.4.2 - 2022-05-26
==============================================

Changes in CUPS v2.4.3 (TBA)
----------------------------

- Added a title with device uri for found network printers (Issues #402, #393)
- Added new media sizes defined by IANA (Issues #501)
- Added quirk for GoDEX label printers (Issue #440)
- Fixed `--enable-libtool-unsupported` (Issue #394)
- Fixed configuration on RISC-V machines (Issue #404)
- Fixed the `device_uri` invalid pointer for driverless printers with `.local`
  hostname (Issue #419)
- Fixed an OpenSSL crash bug (Issue #409)
- Fixed a potential SNMP OID value overflow issue (Issue #431)
- Fixed an OpenSSL certificate loading issue (Issue #465)
- Fixed Brazilian Portuguese translations (Issue #288)
- Fixed invalid memory access during generating IPP Everywhere queue
  (Issue #466)
- Fixed memory leaks in `create_local_bg_thread()` (Issue #466)
- Fixed media size tolerance in `ippeveprinter` (Issue #487)
- Fixed `cupsd` default keychain location when building with OpenSSL
  (Issue #529)
- Fixed TLS certificate generation bugs (Issue #652)
- `ippDeleteValues` would not delete the last value (Issue #556)
- Ignore some of IPP defaults if the application sends its PPD alternative
  (Issue #484)
- Now look for default printer on network if needed (Issue #452)
- Now report fax attributes and values as needed (Issue #459)
- Now localize HTTP responses using the Content-Language value (Issue #426)
- Raised file size limit for importing PPD via Web UI (Issue #433)
- Update print-color-mode if the printer is modified via ColorModel PPD option
  (Issue #451)
- Use localhost when printing via printer application (Issue #353)
- Write defaults into /etc/cups/lpoptions if we're root (Issue #456)


Changes in CUPS v2.4.2 (2022-05-26)
-----------------------------------

- Fixed certificate strings comparison for Local authorization (CVE-2022-26691)
- The `cupsFileOpen` function no longer opens files for append in read-write
  mode (Issue #291)
- The cupsd daemon removed processing temporary queue (Issue #364)
- Fixed delay in IPP backend if GNUTLS is used and endpoint doesn't confirm
  closing the connection (Issue #365)
- Fixed conditional jump based on uninitialized value in cups/ppd.c (Issue #329)
- Fixed CSS related issues in CUPS Web UI (Issue #344)
- Fixed copyright in CUPS Web UI trailer template (Issue #346)
- mDNS hostname in device uri is not resolved when installing a permanent
  IPP Everywhere queue (Issues #340, #343)
- The `lpstat` command now reports when the scheduler is not running
  (Issue #352)
- Updated the man pages concerning the `-h` option (Issue #357)
- Re-added LibreSSL/OpenSSL support (Issue #362)
- Updated the Solaris smf service file (Issue #368)
- Fixed a regression in lpoptions option support (Issue #370)
- The scheduler now regenerates the PPD cache information after changing the
  "cupsd.conf" file (Issue #371)
- Updated the scheduler to set "auth-info-required" to "username,password" if a
  backend reports it needs authentication info but doesn't set a method for
  authentication (Issue #373)
- Updated the configure script to look for the OpenSSL library the old way if
  pkg-config is not available (Issue #375)
- Fixed the prototype for the `httpWriteResponse` function (Issue #380)
- Brought back minimal AIX support (Issue #389)
- `cupsGetResponse` did not always set the last error.
- Fixed a number of old references to the Apple CUPS web page.
- Restored the default/generic printer icon file for the web interface.
- Removed old stylesheet classes that are no longer used by the web
  interface.


Changes in CUPS v2.4.1 (2022-01-27)
-----------------------------------

- The default color mode now is now configurable and defaults to the printer's
  reported default mode (Issue #277)
- Configuration script now checks linking for -Wl,-pie flags (Issue #303)
- Fixed memory leaks - in testi18n (Issue #313), in `cups_enum_dests()`
  (Issue #317), in `_cupsEncodeOption()` and `http_tls_upgrade()` (Issue #322)
- Fixed missing bracket in de/index.html (Issue #299)
- Fixed typos in configuration scripts (Issues #304, #316)
- Removed remaining legacy code for `RIP_MAX_CACHE` environment variable
  (Issue #323)
- Removed deprecated directives from cupsctl and cups-files.conf (Issue #300)
- Removed `purge-jobs` legacy code from CGI scripts and templates (Issue #325)


Changes in CUPS v2.4.0 (2021-11-29)
-----------------------------------

- Added configure option --with-idle-exit-timeout (Issue #294)
- Added --with-systemd-timeoutstartsec configure option (Issue #298)
- DigestOptions now are applied for MD5 Digest authentication defined
  by RFC 2069 as well (Issue #287)
- Fixed compilation on Solaris (Issue #293)
- Fixed and improved German translations (Issue #296, Issue #297)


Changes in CUPS v2.4rc1 (2021-11-12)
------------------------------------

- Added warning and debug messages when loading printers
 if the queue is raw or with driver (Issue #286)
- Compilation now uses -fstack-protector-strong if available (Issue #285)


Changes in CUPS v2.4b1 (2021-10-27)
-----------------------------------

- Added support for CUPS running in a Snapcraft snap.
- Added basic OAuth 2.0 client support (Issue #100)
- Added support for AirPrint and Mopria clients (Issue #105)
- Added configure support for specifying systemd dependencies in the CUPS
  service file (Issue #144)
- Added several features and improvements to `ipptool` (Issue #153)
- Added a JSON output mode for `ipptool`.
- The `ipptool` command now correctly reports an error when a test file cannot
  be found.
- CUPS library now uses thread safe `getpwnam_r` and `getpwuid_r` functions
  (Issue #274)
- Fixed Kerberos authentication for the web interface (Issue #19)
- The ZPL sample driver now supports more "standard" label sizes (Issue #70)
- Fixed reporting of printer instances when enumerating and when no options are
  set for the main instance (Issue #71)
- Reverted USB read limit enforcement change from CUPS 2.2.12 (Issue #72)
- The IPP backend did not return the correct status code when a job was canceled
  at the printer/server (Issue #74)
- The `testlang` unit test program now loops over all of the available locales
  by default (Issue #85)
- The `cupsfilter` command now shows error messages when options are used
  incorrectly (Issue #88)
- The PPD functions now treat boolean values as case-insensitive (Issue #106)
- Temporary queue names no longer end with an underscore (Issue #110)
- The USB backend now runs as root (Issue #121)
- Added pkg-config file for libcups (Issue #122)
- Fixed a PPD memory leak caused by emulator definitions (Issue #124)
- Fixed a `DISPLAY` bug in `ipptool` (Issue #139)
- The scheduler now includes the `[Job N]` prefix for job log messages, even
  when using syslog logging (Issue #154)
- Added support for locales using the GB18030 character set (Issue #159)
- `httpReconnect2` did not reset the socket file descriptor when the TLS
  negotiation failed (Apple #5907)
- `httpUpdate` did not reset the socket file descriptor when the TLS
  negotiation failed (Apple #5915)
- The IPP backend now retries Validate-Job requests (Issue #132)
- Now show better error messages when a driver interface program fails to
  provide a PPD file (Issue #148)
- Added dark mode support to the CUPS web interface (Issue #152)
- Added a workaround for Solaris in `httpAddrConnect2` (Issue #156)
- Fixed an interaction between `--remote-admin` and `--remote-any` for the
  `cupsctl` command (Issue #158)
- Now use a 60 second timeout for reading USB backchannel data (Issue #160)
- The USB backend now tries harder to find a serial number (Issue #170)
- Fixed `@IF(name)` handling in `cupsd.conf` (Apple #5918)
- Fixed documentation and added examples for CUPS' limited CGI support
  (Apple #5940)
- Fixed the `lpc` command prompt (Apple #5946)
- Now always pass "localhost" in the `Host:` header when talking over a domain
  socket or the loopback interface (Issue #185)
- Fixed a job history update issue in the scheduler (Issue #187)
- Fixed `job-pages-per-set` value for duplex print jobs.
- Fixed an edge case in `ippReadIO` to make sure that only complete attributes
  and values are retained on an error (Issue #195)
- Hardened `ippReadIO` to prevent invalid IPP messages from being propagated
  (Issue #195, Issue #196)
- The scheduler now supports the "everywhere" model directly (Issue #201)
- Fixed some IPP Everywhere option mapping problems (Issue #238)
- Fixed support for "job-hold-until" with the Restart-Job operation (Issue #250)
- Fixed the default color/grayscale presets for IPP Everywhere PPDs (Issue #262)
- Fixed support for the 'offline-report' state for all USB backends (Issue #264)
- Fixed an integer overflow in the PWG media size name formatting code
  (Issue #668)
- Documentation fixes (Issue #92, Issue #163, Issue #177, Issue #184)
- Localization updates (Issue #123, Issue #129, Issue #134, Issue #146,
  Issue #164)
- USB quirk updates (Issue #192, Issue #270, Apple #5766, Apple #5838,
  Apple #5843, Apple #5867)
- Web interface updates (Issue #142, Issue #218)
- The `ippeveprinter` tool now automatically uses an available port.
- Fixed several Windows TLS and hashing issues.
- Deprecated cups-config (Issue #97)
- Deprecated Kerberos (`AuthType Negotiate`) authentication (Issue #98)
- Removed support for the (long deprecated and unused) `FontPath`,
  `ListenBackLog`, `LPDConfigFile`, `KeepAliveTimeout`, `RIPCache`, and
  `SMBConfigFile` directives in `cupsd.conf` and `cups-files.conf`.
- Stubbed out deprecated `httpMD5` functions.
- Add test for undefined page ranges during printing.
