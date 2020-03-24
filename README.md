# linux-bash-script-to-backup-restore-tvheadend-server-configuration

This script can be run to backup TVHeadend server configuration (/home/hts/.hts/tvheadend) or restore it from backup (/home/hts/.hts/tvheadend_backup.tar).

I think that it needs super user privilege. So i setup it under root:

sudo su;
cd;wget https://raw.githubusercontent.com/slrslr/linux-bash-script-to-backup-restore-tvheadend-server-configuration/master/linux_tvheadend_server_backup_and_restore;chmod 750 linux_tvheadend_server_backup_and_restore;

test backup:

./linux_tvheadend_server_backup_and_restore backup

test restore:

./linux_tvheadend_server_backup_and_restore restore

setup cronjob to backup let's say every 6 months:

crontab -e

type "a" key

paste/append new line to the crontab opened:

0 0 0 */6 * /bin/bash /root/linux_tvheadend_server_backup_and_restore backup 2&1>/dev/null

Ctrl+C, q, enter
