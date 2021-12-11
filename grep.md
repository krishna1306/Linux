```bash
grep second sample.txt

# Case insensitive search
grep -i second sample.txt

# Recursive search in a directory
grep -r second /home/michael
```

#### Print lines that do not match

```bash
grep -v second sample.txt
```

#### Get exact word match

```bash
grep -w exam examples.txt
```

#### Print lines After and Before a match

```grep
grep -A2 -B2 second sample.txt
```

