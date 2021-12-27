# How to update old paths

In the root directory of the moved website files, run the following command

```bash
grep -rl <oldpath> $d | xargs sed '' 's#<oldpath>#<newpath>#g'
```

where

- `<oldpath>` is the old root path (likely just the course number)
- `<newpath>` is the path to the files in the `past` repo

For example, to link to the summer 2020 version of EDH7916, this was
the following command:

```bash
grep -rl "edh7916" . | xargs sed -i '' 's#edh7916#past/edh7916/2020/summer#g'
```

**NOTE** `sed` will take more than `/` as a delimiter between
`s/OLD/NEW/g`. Since the replacement text has slashes, the hash symbol
`#` works well.
