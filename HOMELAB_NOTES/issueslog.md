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
