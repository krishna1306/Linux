```bash
# Both can be used with same results
ssh user@IP
ssh -l user IP
```

### Password-less SSH

```bash
# On the client
ssh-keygen -t rsa

# Copy the public key on the remote servers '.ssh/authorized_keys' directory
# Also copy the remote server's public key to client's (local) .ssh/known_hosts' 
ssh-copy-id bob@devapp01
```

### SCP

```bash
scp /home/bob/caleston-code.tar.gz devapp01:/home/bob

# p -- preserve permissions and ownerships
# r -- recursive
scp -pr /home/bob/caleston-code.tar.gz devapp01:/home/bob
```

