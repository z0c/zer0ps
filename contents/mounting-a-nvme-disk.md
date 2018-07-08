# Mounting a NVME disk on an EC2 instance

Check if the volume in not mounted yet

```
lsblk
```

Make file system

```
sudo mkfs.ext4 -E nodiscard /dev/nvme0n1
```

Mount the volume

```
sudo mmount -o discard /dev/nvme0n1 /mnt/my-data
```

/dev/nvme0n1 /mnt/my-data ext4 defaults,nofail,discard 0 2
sudo mount -a (check if everything is OK)
sudo reboot


CHECK: https://serverfault.com/questions/433703/how-to-use-instance-store-volumes-storage-in-amazon-ec2
