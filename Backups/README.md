## OPNSense backup

Every day OPNsense uploads a backup to my nextcloud instance

## Docker container backup

Since most persistent volume files from docker containers are pure config files I just run a standard rsync job for the backup, on top of this I make a mariadb backup infrequently that gets uploaded on the same backup job
These are backed up to two different cloud providers using rclone+crypt mounts

## Personal file backup

Same as above, mostly static files that aren't open, rsync is used for this backup also
These are backed up to two different cloud providers using rclone+crypt mounts.

## Switch config backup

TODO
