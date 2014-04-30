zfs-dump
========

Dump ZFS filesystem using zfs send.
It purposely uses syntax very similar to UNIX dump without the tape support.


    Usage: zfs-dump [-#] [-jzr] [-L label] [-f file] filesystem [filesystem...]
        -#          Specify the dump level 0-9. Default: 0 (full backup)
        -j          Compress with bzip2.
        -z          Compress with gzip.
        -r          Recurse through all child filesystems.
        -L          Label to use for snapshots. Default: backup
        -f          Filename to save backup to. Default: STDOUT
        filesystem  Specify the filesystem(s) to dump. Examples: zpool1, tank/home

No restore script has been created yet.  But can be done with ''zfs recv''.
Examples:

    zfs recv destination/file/system < dumpfile
    zcat dumpfile.gz | zfs recv zpool1
