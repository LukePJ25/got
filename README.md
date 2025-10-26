# got
`got` is a basic shell tool for quickly storing, managing, and changing-to directories on your machine. 
Paths can be stored as short keys, allowing you to quickly navigate to a specific directory without needing to type out paths manually.

Yes, this can already be done with symlinks, aliasing, etc.. but this is more-or-less just a product of me trying to further improve my ability to use a shell proficiently, and I figured I'd share it in-case it's of any use to others.

## Usage
The tool is used by adding the file to your bash source:
```
~ $ source "/path/to/file/got"
```
This line can also be added to `~/.bashrc` to be loaded on login.
All keys/paths added are saved to `~/.usergot`. This can be changed as of now by altering the location in the script.

### Saving directories
You can save a directory to a certain key by using the `-a` flag. This will save your present working directory alongside the provided key.
```
~ $ got -a <key>
```
For example, you can save your Documents directory as 'docs' with:
```
/home/johndoe/Documents $ got -a docs
```
Navigating to your Documents folder from anywhere will then be as easy as doing:
```
/home/johndoe/Pictures/Gallery/Paris $ got docs
/home/johndoe/Documents $
```

### Removing directories
You can remove a directory by using the `-r` flag. E.g.:
```
~ $ got -r <key>
```
For example, you can remove your Documents directory saved as 'docs' with:
```
~ $ got -r docs
```

### Overwriting directories
You can overwrite the directory for an existing key by using the `-o` flag. This will overwrite the current path stored for the given key with your present working directory.
```
~ $ got -o <new key>
```
For example, you can overwrite the Documents directory saved as 'docs' with the Music directory by doing:
```
/home/johndoe/Music $ got -o docs
```
