# got
`got` is a basic shell tool for quickly storing, managing, and changing-to directories on your machine. 
Paths can be stored as short keys, allowing you to quickly navigate to a specific directory without needing to type out paths manually.

Yes, this can already be done with symlinks, aliasing, etc.. but this is more-or-less just a product of me trying to further improve my ability to use a shell proficiently, and I figured I'd share it in-case it's of any use to others.

## Usage
The tool is enabled by executing `got` from your terminal, which will add the function to your session:
```
~ $ source "/path/to/file/got"
```
This line can also be added to `~/.bashrc`/`~/.zshrc` to be loaded on a new terminal session.
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

### Removing directory keys
You can remove a directory key by using the `-r` flag. E.g.:
```
~ $ got -r <key>
```
For example, you can remove your Documents directory saved as 'docs' with:
```
~ $ got -r docs
```

### Overwriting directory keys
You can overwrite the directory stored as an existing key by using the `-o` flag. This will overwrite the current directory stored for the given key with your present working directory.
```
~ $ got -o <new key>
```
For example, you can overwrite the Documents directory saved as 'docs' with the Music directory by doing:
```
/home/johndoe/Music $ got -o docs
```

### Listing directories

You can list all stored keys and associated directories with the `-l` flag.
```
~ $ got -l
docs /home/johndoe/Documents
music /home/johndoe/Music
```
