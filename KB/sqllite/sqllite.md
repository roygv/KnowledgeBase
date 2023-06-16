SQLite is a software library that implements a self-contained, serverless, zero-configuration, transactional SQL database engine. SQLite is the most widely deployed SQL database engine in the world. It comes pre-installed on MacOS

## Install
sqlite comes pre-installed on a Mac but it does not allow you to load extensions. If you need to load (or build) your own extensions, you need to install your own copy
```zsh
brew install sqlite
# Make sure the new sqlite is ahead of the buit-in in the PATH
ln -s /usr/local/opt/sqlite/bin/sqlite3 /usr/local/bin/
```
## Load extensions (like md5)
[Many precompiled extensions](https://github.com/nalgeon/sqlean)
Get the prebuilt dynamic library files you need using `curl`  or `git pull`
```bash
> sqlite3
> ...
sqlite> SELECT load_extension("md5.dylib");
```
## Build extensions from C
```bash
gcc -g -fPIC -dynamiclib md5.c -o md5.dylib
```
## Run
```zsh
sqlite3

# To exit, type: .exit
```

## Cheatsheet
https://www.tutorialspoint.com/sqlite/sqlite_commands.htm

## Documentation
[Syntax diagrams](https://www.sqlite.org/lang_expr.html)

