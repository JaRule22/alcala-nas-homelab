# Changelog

## v0.3 - 04-05-2026
### Added
- Created SSD storage pool for cache and transcodes
- Organized media into ALCALAFLIX, ALCALATV, ALCALA4K structure

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
- Created HDD storage pool
- Set up basic shared folders (Movies, TV Shows, docker)
