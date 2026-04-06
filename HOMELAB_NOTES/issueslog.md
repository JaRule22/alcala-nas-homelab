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
