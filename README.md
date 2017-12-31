# cisco-switch-backup
cisco-switch-backup

## Synopsys
This script automates the backup and rotation of Cisco switch configs.

It's been tested using a Catalyst 3750.

## Instructions
Clone the repo and edit the variables to your liking. 
Move or symlink the script into the desired cron directory, I link mine to /etc/cron.daily/

## Configuration
- Switch names must be resolvable by the running machine. IP Addresses will work too.
- SSH Pubkeys need to already exist under the specified user on the switch.
- The script will automatically keep N different copies of your startup config. Older backups are not kept if they match the runtime version of the config.
- Backups are timestamped using epoch time.

## Example
```
abrams ~ # /etc/cron.daily/backup_switches.sh
[*] Getting config for core
[*] Found startup-config for core, saving as /Storage/Backup/switch_configs/core/startup-config.1514693985
[*] No changes found in config, removing old copy of config /Storage/Backup/switch_configs/core/startup-config.1514693631`
```

