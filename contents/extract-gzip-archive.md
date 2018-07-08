# Extract gzip archive

Here's an example of how to extract the contents of a gzip archive via the command line:

```
gzip -d file.gz
```

Finding the size of the archive before extracting

```
$ gzip -l archive.gz
```

alternativelly:

```
$ zcat archive.bz | wc --bytes
```
