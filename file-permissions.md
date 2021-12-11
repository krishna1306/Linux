### Modify File Permissions

```bash
chmod <permissions> filename

# Example - both accomplish the same thing
chmod u+rwx,go+rx test-file
chmod 755 test-file
```

### Change Ownership

```bash
chown owner:group filename

# Recursively
chown -R owner:group filename
```

`group` is optional

```bash
# Modify only group
chgrp group filename
```

