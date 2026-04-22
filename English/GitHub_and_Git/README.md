
# GIT AND GITHUB

---

## Initializing a repository

To start a repository, use the `git init` command inside the directory you want.

![Git Init](img/git_init.png)

---

## Project status

Use `git status` to view the state of the files inside the repository.

![Git Status](img/git_status.png)

---

## Git ignore

If you want to keep certain files or folders hidden from Git, use a `.gitignore` file. Add the names or patterns of files you want Git to ignore.

![.GitIgnore](img/gitignore.png)

---

## User identification

When committing files, we need to identify ourselves so Git knows who created each commit. For that, use `git config user.name "Name"` and `git config user.email "Email"`.

> - ### Configuring locally
>> `git config user.name "First Last"`
>>
>> `git config user.email "email@gmail.com"`
>
> This is recommended when the same computer is used by multiple people.

> - ### Configuring globally
>> `git config --global user.name "First Last"`
>>
>> `git config --global user.email "email@gmail.com"`
>
> This is recommended when the computer is used only by you.

---

## Git add

The `git add` command tells Git to start tracking file changes.

> - ### Add files separately
>> `git add (file name)`
>
> - ### Add all modified files
>> `git add .`

---

## Git commit

`git commit` is used to save a snapshot of your changes. In the message, write a short explanation of what was changed.

> `git commit -m "Committing"`

---

## Git log

`git log` shows the commit history of the repository and the hashes (a hash is the commit identification code).

![`git log`](img/gitlog.png)

> ### Search by keyword

If you want to search more deeply in logs, run `git log` and then type `/keyword`.

`git log`
`/Update`

![Keyword search](img/gitlog_busca_por_palavra.png)

> ### Limit number of logs

If you want to filter to a specific number of commits:

`git log -2`

![Log filtering](img/gitlog_filtragem.png)

### One-line logs

Use the command `git log --oneline`.

![Oneline](img/gitlog_oneline.png)

### Date filters

You can filter logs by date with commands like:

> `git log --after='dd-mm-yyyy'`
>
> `git log --before='dd-mm-yyyy'`
>
> `git log --since='2 days ago'`
>
> `git log --after='3 months ago'`
>
> `git log --before='1 year ago'`
>
> `git log --author='author'`

![](img/gitlog_data.png)

### Git help log

If you need more details, use `git help log`.

---

## Git checkout (hash)

If you want to go back to a previous commit, use `git checkout (hash)`. This makes your files go back in time to that commit state.

![](img/git_volta_no_tempo.png)

To return to the main branch, use `git checkout master/main`.

---

## Renaming files

To rename a file with Git tracking, use `git mv (old name) (new name)`.

> ### Before:
>> ![Before](img/alteracao_de_nome-pt1.png)
>
> ### After:
>> ![After](img/alteracao_de_nome-pt2.png)

---

## Git remove

To remove a file, use `git rm (file or directory name)`.

> ### Before
>> ![Git rm](img/gitrm-pt1.png)
>
> ### After
>> ![Git rm](img/gitrm-pt2.png)

---

## Git diff

`git diff` shows what changed between versions. You can compare with the current commit, with an old hash, or between two hashes.

> ### Compare with current commit
>> ![](img/git_diff_staged.png)
>
> ### Compare current commit with an old hash
>> ![](img/git_diff_hash.png)
>
> ### Compare two different hashes
>> ![](img/git_diff_hash_to_hash.png)

---

## Git commit --amend

`git commit --amend` lets you fix the last commit message when it does not describe the change correctly.

> ### Commit with a wrong message
> ![](img/git_commit_amend-01.png)
>
> ### Fixing the commit
> ![](img/git_commit_amend-02.png)

---

## Going back to the last commit

If you made a bad commit on `main`, you can return files to the previous commit with `git reset HEAD^ --hard`.

> ### Before
>> ![](img/git_reset-pt01.png)
>
> ### After
>> ![](img/git_reset-pt02.png)

---

## Working with branches

A branch is a split from the main project timeline. Think of the main project as a tree and branches as its limbs. The default branch is usually called `master` or `main`.

Use `git branch` to list existing branches.

> ![](img/git_branch.png)

## Creating new branches

To create a new branch, use `git branch (branch_name)`.

> ![](img/git_branch_nome_da_branch.png)

You can also use `git checkout -b (branch_name)` to create and switch to the new branch at once.

![](img/checkout-b.png)

## Switching branches

Use `git checkout (branch_name)` to move between branches.

> ![](img/Alterando_de_branch.png)

## Deleting a branch

To delete a branch, use `git branch -D (branch_name)`.

> ![](img/deletando_branch.png)

---

## Working with merge

If you are working in a branch and want to combine it with the `main` branch, you can use merge.

> ![](img/merge.png)

---

## Rebase

`rebase` is different from merge. Rebase reapplies your branch commits on top of another base, while merge combines histories together.

![](img/rebase.png)

---

## Working with clone

Use `git clone (repository URL)` to create a local copy of a repository.

---

## Working with fetch and pull

`fetch` downloads new data, and then `rebase` or `merge` can reorganize and integrate it. `pull` does both steps together and checks for code updates.

>> ![](img/comandos_pull.png)
>
> Helpful keys for pull workflow
> <br> ^ = Ctrl

---

## Bare repository

Use `git init --bare` to create a bare repository. A bare repository stores only Git data (without a working directory), which is useful as a central remote repository.

---

## Working with tags

`Tags` are used to publish a stable project version separate from `main`.

To create a tag, run `git tag v1.0`. Then push it to the remote with `git push origin v1.0`.

To inspect that version, use `git checkout v1.0`. Remember that, in detached HEAD mode, you usually should not make direct changes there. If you need fixes, create a branch from that tag with `git switch -c update_v1.0.1`, apply changes, merge/rebase as needed, and create a new tag, such as `git tag v1.0.1`.

After that, push the new tag with `git push origin v1.0.1`.

---

## GITHUB

On [GitHub](https://github.com/home), when creating a repository, avoid spaces and special characters in the repository name.
Always create a `README` file to explain the project.

> ![](img/Criacao_de_repositorio.png)

An important point: there are two repository visibility types, private and public. Private repositories restrict who can view the project, while public repositories are visible to everyone and are a good way to showcase your work.

> ![](img/tutorial_de_criacao_de_arquivos_no_github.png)

After creating the repository, [GitHub](https://github.com/home) provides a tutorial to help you use it.

> ![](img/linkagem_do_local_para_remoto.png)

By following the step-by-step instructions, you can connect your local repository to the remote one.

With `git remote -v`, you can check origin URLs.

> ![](img/git_remote-v.png)

After making changes, commit and push with `git push -u origin main`.

---

## Using clone and pull

To clone, copy the repository HTTPS URL.

> ![](img/clone.png)

After copying the URL, run `git clone https://github.com/...`.

> ![](img/clone-02.png)

`git pull` updates your local code when the remote has newer changes. Example: `git pull origin main`.

> ![](img/git_pull.png)

---

## Adding collaborators

Go to repository settings and add collaborators.

![](img/config_rep.png)

After that, collaborators can push to the repository `main` branch (according to permissions).

---

## Undoing checkouts

If you changed files and want to discard local unstaged changes, you can use `git checkout -- .`.

If you want to restore only one file, use `git checkout -- file_name`.

If you staged files with `git add` and want to restore from `HEAD`, use `git checkout HEAD -- .`. For one file, use `git checkout HEAD -- file_name`.

---

## Undoing with revert or reset

> ### Revert

`revert` creates a new commit that undoes a previous commit, keeping history intact.

Use `git revert (hash)`.

![](img/revert.png)

The key advantage of revert is preserving commit history.

> ### Reset

`reset` moves the branch pointer back and can remove commits from the current branch history.

Use `git reset HEAD~1`.
The number indicates how many commits to go back.

![](img/reset.png)

---

## Working with fork

A fork is your own copy of someone else's repository so you can work on it independently.

To do that, open the repository and click the `Fork` button.

![](img/forj.png)

