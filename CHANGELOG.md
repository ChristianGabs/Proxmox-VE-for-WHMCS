# Changelog
All notable changes to Proxmox VE for WHMCS will be documented in this file.

## [1.2.1b] - 2023-06-20

### Added
- Reboot command/action added to Client Area (ie. on/off/hard-off)
- Link from Health tab of Admin GUI to WHMCS Marketplace re: reviews
- Images for all supported Operating Systems & Kernel types (some fixed)
- Ground-work for noVNC overhaul, to support PVE Auth & VNC Tunnel tickets

### Changed
- Stop VM/CT (Client Area) renamed to Hard Stop, compared to Shut Down
- Modify the PHP API2 class, adding getTicket() so we can dual-auth (VNC)
- Move VNC Clients from root-level to vnc-only-level access to Proxmox VE

### Fixed
- noVNC render method updated to stop out-of-order data flow problem
- noVNC back-end vncproxy and vncwebsocket methods updated re: spec
- Client Area actions (Power Off/On, etc) fixed for LXC (QEMU OK)
- Error with both VNC methods. We are going to remove TigerVNC

## [1.2.0b] - 2023-06-18

### Added
- Link off to GitHub Issues for Support from the Module page in WHMCS
- CHANGELOG.md file added to repository to track in recommended format
- Try-catch around the Creation API Call, routing OK/error into WHMCS
- Feed the IP/GW configuration into QEMU and LXC creation attempts
- PVE Storage > Volume Name and Disk I/O Limit fields added (#7)
- Module, PHP & Server reported on the Health/Support GUI tab
- Licensed repository/module via GPLv3 (link-back attribution)
- Warning in README.md re: WHMCS Service ID being > 100
- Zero Tolerance Abuse Policy added to README file

### Changed
- Module versioning changed to semver (semantic versioning) 1.2.0
- Change rel. path to ROOTDIR in IPv4 file, in case of other issues
- Use /cluster/resources via API, not /node/, to get stats (ex. swap)
- Updated noVNC, TigerVNC, Ubuntu, Debian and CentOS interface images
- Improved error handling and pass-back from Proxmox to Class to WHMCS
- Updated the PVE2 API Class and improved its logging (prefix/exception)
- Method to fire API Calls updated due to reduction in WHMCS param scope

### Fixed
- Regression in v1.1 with missing semicolon breaking activation (#14)
- Edit Icon not rendering on IP/Pool edit page, missing asset (#13)
- Relative link to PVE2 API Class file broken, use ROOTDIR (#13/15)
- IPv4 Address functions, update file to use float not real (#13)
- Container (CT/LXC) Swap reporting in Client Area now working
- RRD (Usage) measurements: params attached to requests OK
- API Requests for Creation now functional (fixes #17)
- Client Area pages/actions now fixed (fixes #19)
- Font Awesome icons fixed in the Client Area

## [1.1b] - 2023-06-06
 
### Added
- Swap space editing for plans; back-end existed but not GUI editing
- Modern-day language to GUI according to changes in the 6 years
- README now links out to all Dependencies and Documentation
 
### Changed
- Module Name from "PRVE" to "pvewhmcs" (ie. Proxmox VE for WHMCS)
- Default storage/disk type changed from IDE to Virtio (fastest)
- Updated 3 dependencies to latest: PVE2-PHP, noVNC, TigerVNC
- Removed all code segments relating to Software Licensing
- DNS defaults changed from Google DNS to Cloudflare DNS
 
### Fixed
- Module can now be installed onto WHMCS 8.x installations
- OpenVZ changed to LXC, to support PVE 4.x installs & up
- Removed I/O Priority setting, to re-do via Throttling
- Catch exception in Client Area if can't reach Proxmox

## [1.0] - 2017-01-26

### Added
- Open-sourced the previously commercial plugin

### Changed
- Commented out the licensing code segments

### Fixed
- Removed old database schema import file