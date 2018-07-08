# Resizing linux logical volume

First find out the amount of free space in you volume groups

```
vgdisplay
```

Then look at the attributes of the volume you want to exted

```
lvdisplay /dev/volume-name
```

Then use `lvextend` to add space to the logical volume

```
lvextend --size +4GB /dev/volume-name
```

You can confirm that the size was added by running `lvdisplay` again againt the volume

```
lvdisplay /dev/volume-name
```

Finally extend the file system to use the allocated size

```
resize2fs /dev/volume-name
```

Confirm that the volumes now have the desired sizes

```
df -h
```
