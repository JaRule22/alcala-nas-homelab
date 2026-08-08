## 08/08/2026 - Jellyfin app "Server Offline"

### Issue
Jellyfin app returned "Server offline / Error contacting Jellyfin server" via jellyfin app over cellular data.
Web browser could reach the domain but Chrome showed NET::ERR_CERT_DATE_INVALID after clicking through warning.

### Cause
- SSL certificate for alcalaflix.com expired on 08/06/2026. Let's Encrypt auto-renewal via Ngix Proxy manager failed silently
- Possibly happened during a recent router reset, which was suspected as the cause (re-added port 80/443 forwarding after reset)
- Also discovered during troubleshooting that Cloudflare AAAA (IPv6) record was stale, and that the home network currently has no active IPv6 connectivity at all. Not the root cause but good to know.

### Solution
- In Nginx Porxy Manager -> Proxy Host -> SSL tab -> Request a new SSL Certificate for alcalaflix.com. New cert valid until 11/06/2026
- removed the stale Cloudflare AAAA record.
- Would need to follow up and check if the auto-renewal didn't activate at 11/06/2026
  
## 05/27/2026 - Remote Jellyfin access issues

### Issue
When someone tries to access my server using it's domain (https://alcalaflix.com), it will load and then
it times out.

### Cause
- Got a new router

### Solution
- Forward ports again for web access. Port 80 (HTTP) and 443 (HTTPS).

## 05/09/2026 - Remote Jellyfin Playback Buffering and Playback Failures

### Issue
Remote user experience:
- Playback freezing
- Buffering
- White pixelated screen artifacts
- Subtitle/audio switching failures
- Unstable Apple TV & Swiftfin playback

### Cause
- Raw Blu-ray remuxes exceeded available remote upload bandwidth
- Movies were direct playing very high bitrates (~40-80+ Mbps)
- Apple TV client struggled with large remux bitrate spikes during remote playback

### Solution
- Enabled GPU performance mode and privileged mode for Jellyfin container
- Implemented HandBrake compression workflow for streaming-friendly copies
- Configured remote bitrate limit to 8 Mbps on Jellyfin
- Migrated ALCALAFLIX library toward compresses H.264 streaming copies

## 05/08/2026 - Nginx Proxy Manager SSL Certificate Failed to Generate

### Issue
Nginx Proxy Manager failed to generate a Let's Encrypt SSL certificate for alcalaflix.com

### Cause
- Incorrect Docker/NPM port mapping config
- External ports 80 and 443 were not properly mapped to container ports
- NPM container permissions caused certificate generation issues
- Remote HTTP validation requests could not properly reach the NPM container

### Solution
- Corrected Docker Port mappings for ports 80, 81, and 443
- Configure Spectrum router port forwarding ports 80 and 443
- Enabled privileged mode for the NPM container
- Verified Cloudflare DNS config was set to DNS only
- Restarted NPM container and successfully regenerated SSL certficates

## 04/06/2026 - Jellyfin docker container has failed to start

### Issue
The jellyfin docker container failed to start as a source path does not exist: /volume1/docker/jellyfin_jellyfin-1/cache

### Cause
I have made a change on the files after creating the jellyfin docker container. I have organized performance based files to my SSDs and the more bulky permanent files to the HDDs. This was the cause of the error.

### Solution
Edited in Docker where the cache files are located and changed the source path to volume 2. All objects work and features work properly on jellyfin.


## 04/05/2026 - UGREEN NAS not detected by discovery tool

### Issue
The UGREEN NAS Finder tool was unable to detect the NAS on the network.

### Cause (suspected)
Network discovery service did not properly resolve the device on the local network?

### Solution
Accessed the NAS directly by entering its IP address into the browser instead of using the discovery tool.

### Result
Successfully accessed the NAS management interface and confirmed the device was online and reachable.
