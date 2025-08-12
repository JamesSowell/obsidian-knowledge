

# Under the Hood
is an Object Database, using SHA52's of the file that you wish to encode. uses Zedlib to compress the data such that it has those crazy symbols that you wouldnt' ordinarilly use.
>git hash-object <-w>

Git's object Database is a key component of its architecture. It stores four different types of objects:
1. Blobs: Represent file data
2. Trees: Represent directories and their contents
3. Commits: represents snapshots of the  of the repository at a point in time
4. Tags: Represent named references to commits

These objects are stored in a *DAG* where commits point to trees, trees point to blobs, and commits can point to parent commits


|                                              |                                                                                 |
| -------------------------------------------- | ------------------------------------------------------------------------------- |
| `git hash-object`                            | Hash a file (or stdin) into a blob (optionally write it to the database).       |
| `git cat-file -p <sha>`                      | Pretty-print a Git object (blob, tree, commit, or tag) by SHA.                  |
| `git cat-file -t <sha>`                      | Tell you the _type_ of an object (blob, tree, commit, tag).                     |
| `git ls-tree <tree-sha>`                     | List the contents of a tree object (shows blobs and sub-trees).                 |
| `git write-tree`                             | Create a tree object from the current staged files (from the index).            |
| `git read-tree`                              | Load a tree into the staging area (index) — advanced, sets up repo state.       |
| `git commit-tree <tree-sha> -p <parent-sha>` | Create a commit manually from a tree (optionally specifying parent commits).    |
| `git rev-parse <ref>`                        | Resolve a name (like `HEAD`, `master`, etc.) to a full SHA.                     |
| `git update-index`                           | Manually manipulate the index (staging area).                                   |
| `git rev-list <commit-sha>`                  | List all ancestors of a commit (traverse commit graph).                         |
| `git fsck`                                   | Check internal object database for errors (and lists all objects).              |
| `git show-index`<br>                         | Show what's inside `.git/index` (the staging area). (low-level and a bit messy) |
|                                              |                                                                                 |
|                                              |                                                                                 |
**origin**
is the *shorthand* name for the remote repository that a project was originally cloned from. 

***index (AKA 'Staging Area')***
the liminal space in which the *tracked* changes are STORED before actually *hashed* and stored as an object in the **DB**, effectively adding it to the **repo**
- Therefore when performing a `git branch -f ftr previous commit` you're effectively moving a ptr to a previous commit but that commit that you are leaving may now be a *memory leak*!
- however when performing a `git reset previous_commit`
- the garbage collect may eventually handle cleaning up any *unused/unreachable* commits
- `git gc` is used to *manually* run the Garbage collector!

***NOTE***: you'll have to use *--force* to push changse when using `branch -f` or `git reset`

Today marks the best day of the worst part of your life. 

```python
dp = [] * n
for i in range(n):
	for j in range(m):
		A[i][j] = dp[i-1][j-1]
```


`HEAD->main, tag: x.x.x, origin/main, origin/HEAD` the *branching* from local vs *remote*, 
1. The first is the *local* representation of your repo. 
2. origin/main: is the remote branch 'main' on the remote named *origin*


*3*. origin/HEAD: is the symbolic refenrec to the HEAD of the remote repository *origin*

`git push origin main --force` must be used if you're rewriting commit history on your local.
***WARNING:*** This can be destructive if not used carefully. 

# Git Branching Game
**Rebase**
I learned that you can use the `-i` flag to toggle *interactive* mode, which opens an *editor*:
- You can effectively *choose* which commits and the Messages for each that you want! inclucing *squashing*! 
oo

 = 0, m-1
```python
 for i in range(n):
	 for j in range(m):
		 # we can perform bitwise manipulator
for subset in range(1, n+1S)
```


# Authentication and linking git account.
git comes with small linux commands, one of such is
`ssh-keygen` which generates a cryptograhic key-pair (private + public /) for use with SSH,
[[Cryptography]]

ed25519
: Ed25519 elliptic curve algorithm (better than RSA)

`~/.ssh/id_ed25519` *private key*
`~/.ssh/id_ed25519.pub` *public key*

therefore when running 
`ssh -T git@github.com` 
1. Git says 'prove who you claim to be' (from looking at your user.email)
2. you sign something with your *private* key which lives on your machine
3. Github uses the public key that you gave it to make sure you are who you say you are!

#link to what I know about encryption 


when you set up .ssh/config


know whether your repo uses `ssh` or `https`
```bash
git remote -v
```


# note about SSH
git doesn't occupy your *ssh* tech, Git has their statndard when their *Repo* starts with `git@...` that it means look to your ssh, we are not doing *HTTPS*


`Host github.com
  HostName github.com
  User git
  IdentityFile ~/.ssh/id_ed25519`
  
This tells SSH:
> Whenever someone says “ship this to github.com,” use these details:
> - Go to `github.com` (DNS name)
> - Use the `git` account there
> - Bring along this specific key (`id_ed25519`)