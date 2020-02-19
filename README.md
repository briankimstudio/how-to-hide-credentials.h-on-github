**How to hide credentials.h on github**

1. Commit dummy credentials.h
2. Add to .gitignore
3. Untrack it
4. Copy original credentials.h back to working directory

Batch file for teseting on Windows command line. .gitignore seems recognizes only '/' even on Windows environment.
```
git init
mkdir config
touch config/credentials.h
touch hello.c
git add .
git commit -m "initial"
echo config/credentials.h > .gitignore
git add .
git commit -m "update gitignore"
git rm --cached config/credentials.h
git commit -m "untrack credentials.h"
ls >> config/credentials.h
git status
```

Clean up environment
```
rm .gitignore hello.c
rm -rf .git config
```
