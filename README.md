# Useful Syntax/Command/Codes


## **Git**

#### Reverting Commits
You could get merge conflicts, if you've modified things which were changed since the commit you reset to:

    `git revert <commit_id> <commit_id> <commit_id> ...`

    **resolves issues**

    `git commit -m ...`

This will destroy any local modifications: `git reset --hard <commit_id>` (Don't do it if you have uncommitted work you want to keep.)

#### Alternative
    `git stash`

    `git reset --hard <commit_id>`

    `git stash pop`
    
#### Branching Out

`git pull`

`git switch main`

`git checkout -b <new_branch> main`

#### Merge into Branch

`git checkout <branch_name>`

`git merge origin/main`




## **vi** Editor
- **$ vi <filename>**— Open or edit a file.
- **i** — Switch to Insert mode.
- **Esc** — Switch to Command mode.
- **:w** — Save and continue editing.
- **:wq** or ZZ — Save and quit/exit vi.
- **:q!** — Quit vi and do not save changes.
- **yy** — Yank (copy) a line of text.
- **p** — Paste a line of yanked text below the current line.
- **o** — Open a new line under the current line.
- **O** — Open a new line above the current line.
- **A** — Append to the end of the line.
- **a** — Append after the cursor’s current position.
- **I** — Insert text at the beginning of the current line.
- **b** — Go to the beginning of the word.
- **e** — Go to the end of the word.
- **x** — Delete a single character.
- **dd** — Delete an entire line.
- **Xdd** — Delete X number of lines.
- **Xyy** — Yank X number of lines.
- **G** — Go to the last line in a file.
- **XG** — Go to line X in a file.
- **gg** — Go to the first line in a file.
- **:num** — Display the current line’s line number.
- **h** — Move left one character.
- **j** — Move down one line.
- **k** — Move up one line.
- **l** — Move right one character.
