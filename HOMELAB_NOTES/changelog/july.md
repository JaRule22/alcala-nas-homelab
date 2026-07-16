# Changelog
## v0.7 - 07-16-2026
### Added
- Added a Tailscale container via Docker to transfer files.

### Changed
- I was visiting my family and had remote access to my NAS, I wanted to transfer files from my parents' network to my home network to my NAS. I chose Tailscale because I did not want to expose my NAS directly to the internet or forward more ports.
 
### Improved
- Improved easier and secure access to my NAS anywhere.
- Better security by avoiding exposing services like SMB to the internet through port forwarding.
- No more worrying about changing IP addresses since Tailscale's IP address.
- Less router conifguration.
- My parents' network could potentially be an off-site backup for my NAS via Tailscale.
