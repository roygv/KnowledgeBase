[See presentation](https://github.com/git-school/git-under-the-hood/blob/master/demystifying-git-slides.pdf) about the internal structure of the .git folder

## Commands
List files in .git folder along with blob ids: `git ls-files -s`
Show content of a blob: `git cat-file -p <blob id>`
show type of a blob: `git cat-file -t <blob id>`
