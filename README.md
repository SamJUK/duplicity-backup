# Duplicity Backups

## Installation
```
apt install duplicity python3-b2sdk -y
sudo git clone {THIS_REPO} /opt/backup
```

## Configuration
- Create `/opt/backup/config.env`
- Overwrite any `CONFIG__` property from backup script

## Usage
```
# Create a backup
/opt/backup/backup backup

# Get Duplicity configured DSN
/opt/backup/backup dsn

# List backed up files
/opt/backup/backup list-files /databases

# Restore whole backup
/opt/backup/backup restore /files /tmp/my_restored_site
/opt/backup/backup restore /databases /tmp/my_restored_databases

# Restore a single file
/opt/backup/backup restore-file /databases /tmp/dev.sql dev.sql
```

## Auto Backup
Add to crontab
```
7 0 * * * /bin/bash /opt/backup >> /opt/backup/backup.log
```