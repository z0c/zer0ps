# fsck

fsck (file system consistency check) is an utility that scans file systems for errors and potentially repairs them.

**IMPORTANT!**

fsck should only run on an unmounted disk or risk losing data and corrupting the file system.

## How to use

1. First make sure the disk is not mounted. The following command should not show the disk in the listing

```$ df -h
```

2. If the device is mounted, unmount it before proceeding (ex. `/dev/sdb`)

```$ unmount /dev/sdb
```

3. Find which device to target the scan
```$ fdisk -l
```

4. Scan the disk, the `-y` switch enable the interactive repair mode
```$ fsck -a /dev/sda1
```
