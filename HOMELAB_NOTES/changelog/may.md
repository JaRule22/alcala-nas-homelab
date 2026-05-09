# Changelog
## v0.6 - 05-09-2026
### Added
- Added HandBrake compression for optimized remote streaming copies
- Added H.264 encoding pipeline for streaming-friendly media

### Changed
- Because there was an issue with transcoding and movie buffering issues I changed the remote streaming bitrate limit to be 8 Mbps for stability. We tested with the new bit rate and it works smoothly. By default, the bit rate was set to 60 Mbps which explains why the movies were slowing down bad.
- Changed media workflow from remux-only storage to hybrid streaming architecure
  - Was: DVD->MakeMKV->File .MKV->JellyFin
  - Now: DVD->MakeMKV->HandBreak compression->File .MKV->JellyFin
  - Compression will only be used movies for streaming (ALCALAFLIX, ALCALATV, etc.)
  - Compression will not be used for 4K movies and will only be available locally(ALCALA4K)
 
### Improved
- Improved remote playback smoothness by reducing bitrate spikes
- Improved multi-user streaming scalability
- Improved upload bandwidth efficiency for external Jellyfin users
- Improved compatibility with Apple TV users.

## v0.5 - 05-09-2026
### Added
- Configured remote Jellyfin access using Nginx Proxy Manager reverse proxy
- Configured Cloudflare DDNS for automatic public IP updates
- Added HTTPS/SSL support for alcalaflix.com
- Added remote Jellyfin streaming outside local network
- Added Spectrum router port forwarding configuration ports 80 and 443
- Added Intel Quick Sync GPU acceleration and Jellyfin transcoding
- Added dual-library structure:
  - ALCALAFLIX for compressed streaming media
  - ALCALA4K for archival remuxes and local playback
- Created a user for testing outside of LAN

### Changed
- Changed Jellyfin container configuration to support GPU acceleration and remote playback

### Improved
- Improved Jellyfin remote accessibility and HTTPS security
