# Changelog

## v0.4 - 04-06-2026
### Added
- Enabled UGREENLink remote access

### Changed
- Enabled "Automatically redirect HTTP connection to HTTPS

### Improved
- Auto redirection HTTP->HTTPS forces all connections to use secure encryption instead of plain HTTP
- I can now access my NAS otuside of my home network
- Improved login credential and system security

## v0.3 - 04-05-2026
### Added
- Created SSD storage pool for cache and transcodes (Volume 2)

### Changed
- Moved Jellyfin cache directory to SSD pool for better performance
- Updated Docker volume paths to reflect new storage layout

### Improved
- Faster media browsing and reduced buffering in Jellyfin
- Cleaner separation between HDD bulk storage and SSD performance storage

---

## v0.2 - 04-05-2026
### Added
- Installed Docker on NAS
- Deployed Jellyfin media server container

### Changed
- Configured media directories for Movies and TV Shows

---

## v0.1 - 04-05-2026
### Added
- Initial NAS setup
- Created HDD storage pool (Volume 1)
- Set up basic shared folders (Movies, TV Shows, docker)
