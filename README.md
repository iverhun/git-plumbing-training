# Agenda

1. Intro. Git as file system.
2. Git eficiency examples (storage, network)
3. Create empty directory. Show that it's not a goit repo (`git status`)
4. Create `.git` dir. Show that it's not a goit repo (`git status`)
5. Create `objects`, `refs/heads`, `refs/tags` folders and `HEAD` file. Show that it's not a git repo (`git status`)
6. add the following line to `HEADS`: `ref: refs/heads/master`. Run `git status`
7. Blobs. `git hash-object` examples:
  1. `echo "git is awesome" | git hash-object --stdin`
  2. `git hash-object <filename>`, 
  3. add `-w`, show contents of `.git/objects` folder. Explain directories naming 
  4. write identical file, show that the hash is the same
  5. write different file, show that the hash is different, show another blob inn the repository
8. `git cat-file`, `-t` (type) and `-p` (pretty-print) options 
9. Explain concepts: 
  1. working directory
  1. index/cache/staging area
  2. repository
10. Add to index: 
  1. create subfolder, add file to subfolder
  2. `git update-index --add --cacheinfo 100644 <blob-hash> <filename>` and variations:
    3. existing file (previously written to a repo with `git has-object -w`)
    4. non-existing file, 
    5. existing file but with content different that in the blob
11. Tree:
  3. create untracked file (don't add it to the index)
  3. `git write-tree`
  4. `git cat-file` for the created tree
12. Commits:
  6. create commit: `git commit-tree <tree-hash> -m <commit message>`
  7. `git cat-file` for commit
  8. create commit with parent commit
  9. Explain that git history is a snapshot of the state of the tree, not a sequence of diffs
13. Branches, HEAD:
  10. create 2 branches by creating 2 files in `.git/refs/heads` folder. Point branches to specific commits
  11. change reference in the `HEAD` file to another branch. Show the result with `git branch`
  12. Summary: branches and `HEAD` are jus references (as well as tags)
14. `git fsck`
15. Show visual learning tools:
  15. http://git-school.github.io/visualizing-git/ 
    16. Demonstrate `merge` vs `rebase`
  17. https://learngitbranching.js.org
18. Tell about alternative (non-SCM) git use cases

# Additional Resources
https://github.com/pluralsight/git-internals-pdf
https://blog.thoughtram.io/git/2014/11/18/the-anatomy-of-a-git-commit.html
https://jwiegley.github.io/git-from-the-bottom-up/1-Repository/5-the-beauty-of-commits.html
https://www.freecodecamp.org/news/git-internals-objects-branches-create-repo/
https://aboullaite.me/deep-dive-into-git/
https://gitolite.com/uses-of-index.html
https://www.chromium.org/developers/fast-intro-to-git-internals
