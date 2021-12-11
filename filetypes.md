1. Regualr files
2. Directories
3. Special files
   1. Character files `/dev` (mouse, keyboard)
   2. Block files `/dev` (hard disks)
   3. Links
      1. Hard links (same inodeb)
      2. Soft links (different inodeb)
   4. Socket files
   5. Named pipes

#### Determine File Type

```bash
file <filename>
```

or just do

```bash
ls -lrt <filepath>
```

_Look for the first letter. That shows the file type_

