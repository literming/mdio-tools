ChangeLog
=========

All notable changes to the project are documented in this file.

[v1.2.0] - 2022-09-15
---------------------

### Added
- mdio: A new addressing mode "mmd-c22": Used to access MMDs attached
  to MDIO controllers without Clause 45 support by using registers 13
  and 14 in the device's Clause 22 register space
- mdio: Pretty print gigabit link capability information from a PHY's
  extended status register
- mdio: Pretty print lots of status information from MMDs (C45 PHYs)
- mvls: Decode priority override information of ATU entries

### Changed
- mvls: Table listings now always prints out the device information,
  even on single chip systems.

[v1.1.1] - 2022-05-23
---------------------

Tiny bugfix release.

### Fixed
- mdio: The bench operation is now much more reliable when stacked on
  other devices than regular PHYs (e.g. paged PHYs or Marvell
  switches).
- mvls: The STU can now be dumped chips from the Peridot generation.

[v1.1.0] - 2022-05-04
---------------------

A sprawling release, adding various mvls related introspection
features. mvls also gains a JSON output format.

### Added
- mvls: The STU can now be dumped (requires Linux 5.17 or later). This
  is useful now that mv88e6xxx supports offloading of MST states
- mvls: Output can now be formatted as JSON for easier scripting
- mdio: mvls: A subset of MIB counters can now be dumped. This let's
  you get at counters for DSA ports, which are not reachable from
  ethtool
- mdio: mvls: The LAG mask and LAG map tables can now be dumped
- mdio: Improve usage message by including the examples from the
  manual

[v1.0.1] - 2021-11-26
---------------------

Primarily fixes a few issues in the kernel module that were found
during a quick review from Russell King:

https://lore.kernel.org/netdev/YYPThd7aX+TBWslz@shell.armlinux.org.uk/
https://lore.kernel.org/netdev/YYPU1gOvUPa00JWg@shell.armlinux.org.uk/

### Added
- mdio: The mvls subcommand now supports flushing the ATU

### Fixed
- mdio-netlink: Plug some glaring holes around integer overflows of
  the PC.
- mdio-netlink: Release reference to MDIO bus after a transaction
  completes.


[v1.0.0] - 2021-09-17
---------------------

### Added
- Basic usage text, `mvls -h`
- Manuals

### Changes
- Reworked command syntax to be more ergonomic
- Improved error output

### Fixes
- Fix #4: buffer alignment on Arm9 systems

### Removed
- References to the dump operation in mdio(8) which is not supported
  at the moment

v1.0.0-beta1 - 2021-05-21
-------------------------

Initial public release.


[UNRELEASED]: https://github.com/wkz/mdio-tools/compare/1.0.0-beta1...HEAD
[v1.0.0]:     https://github.com/wkz/mdio-tools/compare/1.0.0-beta1...1.0.0
