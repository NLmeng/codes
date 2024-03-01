# Useful Syntax/Command/Codes


## **Git**
    
    
#### Branching Out

    git pull

    git switch main

    git checkout -b <new_branch> main


#### Merge into Branch

    git checkout <branch_name>

    git merge origin/main


#### Setting email for a single repository

    Change the current working directory to the local repository where you want to configure the email address:

        git config user.email <email>

    Confirm that you have set the email address correctly in Git:

        git config user.email

#### Setting email globally

`git config --global user.email <email>`

Here's how to include the instructions for cloning and pushing a repository using Git, specifically focusing on the use of bare repositories and mirror pushing for transferring or duplicating repositories. This addition complements the section on useful Git commands and practices.


#### Reverting Commits
You could get merge conflicts, if you've modified things which were changed since the commit you reset to:

    git revert <commit_id> <commit_id> <commit_id> ...

    **resolves issues**

    git commit -m ...

This will destroy any local modifications: `git reset --hard <commit_id>` (Don't do it if you have uncommitted work you want to keep.)

#### Alternative
    
    git stash

    git reset --hard <commit_id>

    git stash pop


#### Clone a Repository (Bare Clone)
To clone a repository without a working directory (bare clone), which is useful for transferring a repository:

    git clone --bare <repository_url>

This command creates a bare clone of the repository. A bare clone is essentially a copy of the repository's .git directory and does not include any of the files in the working directory.

#### Push to New Repository (Mirror Push)
After creating a bare clone, use the following command to mirror-push to a new repository. This is useful for transferring a repository to a new location while preserving its Git history:

    git push --mirror <new_repository_url>

This command pushes all refs (branches, tags, etc.) along with their respective commits to the new repository. It's an effective way to transfer the entire repository to a new location.

#### Cleanup After Transfer
After successfully mirror-pushing to a new repository, you may want to remove the temporary local repository created during the process:

    cd ..
    rm -rf <bare_repository_folder>

Replace `<bare_repository_folder>` with the name of the folder created during the bare clone process. This step is optional but helps in cleaning up unnecessary files from your local machine.

This workflow ensures that the entire repository, including all its branches, tags, and commit history, is transferred to the new location.


#### Rewriting Commit History (changing your OWN previous commit histories)

    git filter-branch -f --commit-filter '
      if [ "$GIT_AUTHOR_EMAIL" = "wrong@email1.com" ] || [ "$GIT_AUTHOR_EMAIL" = "wrong@email2.com" ];
      then
              GIT_AUTHOR_NAME="FirstName LastName";
              GIT_AUTHOR_EMAIL="correct@email.com";
              git commit-tree "$@";
      else
              git commit-tree "$@";
      fi' HEAD
      
    git push --force origin
    
**this is strictly for associating your past commits to your current GitHub, useful incases where you did not set up your SSH in the past**

`%h=commit-code, %s=commit-message, %b=all details`
#### Check all emails in commit history
`git log --pretty="%an <%ae>" --all | sort -u`

#### Check all commit by an author
`git log --author="AUTHOR" --pretty=format:"%h - %s"`

#### Check all co-authored commit by an author
`git log --grep="Co-authored-by: AUTHOR" --all --pretty='%h - %s'`

#### Check all remotes
`git remote -v`

#### Adding remotes
`git remote add <name> <url>`

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
