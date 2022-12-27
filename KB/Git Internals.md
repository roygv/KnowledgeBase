[See presentation](https://github.com/git-school/git-under-the-hood/blob/master/demystifying-git-slides.pdf) about the internal structure of the .git folder

## Internal commands
--List files in .git folder along with blob ids
`git ls-files -s`
--Show content of a blob
`git cat-file -p <blob id>`
--show type of a blob
`git cat-file -t <blob id>`

## List changed files
-- Show changed files between working tree and index (staging area)
git status
-- Show changes between two branches or between local and remote
git status 

## Compare files content (using diffs)
-- Comapre all working tree with index (staging area). Result can be added with git-add
`git diff`
-- Comapre a file in the working tree with index
`git diff <path to file>`
-- Compare index to the branch/HEAD/commit
`git diff [HEAD | <branch name> | commit]`


