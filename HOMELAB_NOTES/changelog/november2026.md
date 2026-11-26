# Changelog
## v1.0 - 11-25-2026
### Added
- Added an API token(npm-dns-alcalaflix) for my NPM server 

### Changed
- NPM server now uses an API token to log into the Cloudflare's API, creates a TXT record, and verifies if I own the domain.
 
### Improved
- alcalflix.com site is encrypted and browsers can verify if it is really my server
- Port 80 is not needed for validation anymore. THe HTTP challenge forced port 80 to stay reachable from the internet.
- Improved Least Privilege. The token can only edit DNS for one domain, so NPM never hold my full Cloudflare login
