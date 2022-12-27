[See presentation](https://github.com/git-school/git-under-the-hood/blob/master/demystifying-git-slides.pdf) about the internal structure of the .git folder

## Commands
List files in .git folder along with blob ids: `git ls-files -s`
Show content of a blob: `git cat-file -p <blob id>`
show type of a blob: `git cat-file -t <blob id>`

## Compare files content (using diffs)
-- Comapre all working tree with index (statging area)
`git diff`
-- Comapre a file in the working tree with index
`git diff <path to file>`
-- Compare index to a branch
`git diff <branch name>`

