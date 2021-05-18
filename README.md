
apt install sshpass

Before first use, go to sftp via console to add RSA key to the list of known hosts
    
    Usage: /root/mysql-sftp-backups/backup [OPTION]... [DATABASE|FILENAME PATH]...

    Options:                    Description:
    -h, --help                  display this help and exit
    -l, --list                  display all saved backups
    --log                       display log file

    Usage with argument [DATABASE]
    -c, --create                create backup from database[s...]

    Usage with argument [FILENAME PATH]
    -r, --restore               restore database from filename path

    Usage CAUTION!!!
    --clean                     cleaned all backups

    Examples:

    create backups from 3 databases
    /root/mysql-sftp-backups/backup -c database_1 batabase_2 database_3
    or
    /root/mysql-sftp-backups/backup --create database_1 batabase_2 database_3
    or from crontab command
    /root/mysql-sftp-backups/backup --create database_1 batabase_2 database_3 >/dev/null 2>&1

    restore database_1 from sftp backup file
    /root/mysql-sftp-backups/backup -r /mysql-sftp-backups/database_1/database_1_2021-05-18-06-47-42.sql.gz
    or
    /root/mysql-sftp-backups/backup --restore /mysql-sftp-backups/database_1/database_1_2021-05-18-06-47-42.sql.gz

    display list all backups files on ftp server
    /root/mysql-sftp-backups/backup -l
    or
    /root/mysql-sftp-backups/backup --list