```bash
# check file size
du -h <file-name>

# shows size in kb
du -sk test.img
```

#### Archiving

```bash
# create a tar file
tar -cf test.tar file1 file2 file3 file4

# use gzip algorithm to compress
tar -zcf test.tar file1 file2 file3 file4

# list contents of a tar ball
tar -tf test.tar

# extract contents of a tar ball
tar -xf test.tar
```

#### Popular compression tools

Compression tools are used to compress files (`.tar` is also a file)

```bash
bzip2 test.img
bunzip2 test.img.bz2

gzip test1.img
gunzip test.img.gz

xz test2.img
unxz test2.img.xz
```

#### Read compressed files without uncompressing them

```bash
bzcat file1.bz2
zcat file1.gz
xzcat file1.xz
```

