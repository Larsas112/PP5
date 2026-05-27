# PP5

## Goal

In this exercise you will:

* Use Git **locally** on your own machine: create branches, make commits, and merge them back.
* Set up and interact with a **bare** Git repository on an SSH‐accessible server (e.g. **vorlesungsserver**, or any machine you have SSH access to).
* Push and pull to/from **GitHub** and the **THGA GitLab** server.
* Practice **forking** an existing repo, making changes, and submitting a **Pull Request** (on GitHub) or **Merge Request** (on GitLab).

**Important:** Start a stopwatch when you begin and work uninterruptedly for **90 minutes**. Once time is up, stop immediately and document exactly where you had to pause.

---

## Workflow

1. **Fork** this repository
2. **Modify & commit** your solution
3. **Submit your link for Review**

---

## Prerequisites

* Several starter repos are available here:
  [https://github.com/orgs/STEMgraph/repositories?q=Git%3A](https://github.com/orgs/STEMgraph/repositories?q=Git%3A)
* Ensure you have **SSH access** to a remote server (e.g., “vorlesungsserver”).
* Throughout, consult Git’s built-in man-pages (`git help <command>`) for explanations and options.

---

## Tasks

### Task 1: Local Git – Branching & Merging

1. Create a new directory in your home directory and initialize a repository in it. 
2. In one of your cloned repos, initialize a new branch called `feature-1`.
3. On `feature-1`, create a file `feature.txt` containing a short description of what you’re doing.
4. Commit your changes, then switch back to `master` (or `main`), and merge `feature-1` into your `master`.
5. Resolve any merge conflicts (if they arise) by hand, then commit the merge. 

**Your Commands & Output**

```bash
# Paste here the sequence of git commands you ran
Habe leider zunächst im master die feature-datei erstellt und bin deswegen für den merge auf feature-not1 gewechselt.
   68  mkdir PP5
   69  ls
   70  cd PP5
   71  git init
   72  vim feature.txt
   73  git status
   74  git add feature.txt
   75  git status
   76  git commit
   77  cd
   78  git config
   79  git config --global user.email "lars.sandkuehler@stud.thga.de"
   80  git config --global user.name "Lars"
   81  cd PP5
   82  git commit
   83  vim feature.txt
   84  git add feature.txt
   85  git commit
   86  git help merge
   87  cd PP5/
   88  git log
   89  git checkout 3ef6
   90  vim feature-not1.txt
   91  git add feature-not1.txt
   92  git status
   93  git commit
   94  git-merge
   95  git help merge
   96  git merge
   97  git status
   98  git checkout master
   99  git merge
  100  git merge bb8ca0f
  101  git status
  102  ls
  103  history
# and the relevant terminal output (e.g., branch listing, merge messages)
commit cff1f68efacffe01ba86f9737601241e276f8423 (HEAD -> master)
Author: Lars <lars.sandkuehler@stud.thga.de>
Date:   Wed May 27 20:21:08 2026 +0200

    feature-1

    Neuer commit jetzt mit korrektem commit-Namen.

commit 3ef65f66e654806f5436716c4eeb5a00191e6372
Author: Lars <lars.sandkuehler@stud.thga.de>
Date:   Wed May 27 20:12:56 2026 +0200

    Leeres repo

    Erstellung von feature.txt mit Kurzbeschreibung meiner Tätigkeit.

    feature.txt vorhanden


Merge made by the 'ort' strategy.
 feature-not1.txt | 1 +
 1 file changed, 1 insertion(+)
 create mode 100644 feature-not1.txt

```

---

### Task 2: Bare Repository on an SSH Server

1. On your SSH server (e.g., “vorlesungsserver”), create a **bare** repo at `~/repos/myproject.git`:

   ```bash
   ssh youruser@vorlesungsserver \
     "mkdir -p ~/repos/myproject.git && cd ~/repos/myproject.git && git init --bare"
   ```
2. On your local machine, add it as a remote named `origin-ssh`:

   ```bash
   git remote add origin-ssh youruser@vorlesungsserver:~/repos/myproject.git
   ```
3. Push your `master` branch to `origin-ssh`, then clone it into a fresh directory to verify.

**Your Commands & Output**

```bash
# Paste here the push & clone commands and outputs
git push --set-upstream origin-ssh master

Enumerating objects: 11, done.
Counting objects: 100% (11/11), done.
Delta compression using up to 12 threads
Compressing objects: 100% (9/9), done.
Writing objects: 100% (11/11), 1.27 KiB | 259.00 KiB/s, done.
Total 11 (delta 1), reused 0 (delta 0), pack-reused 0 (from 0)
To vorlesung:~/repos/myproject.git
 * [new branch]      master -> master
branch 'master' set up to track 'origin-ssh/master'.

git clone Lars311739@vorlesung:~/repos/myproject.git

remote: Enumerating objects: 11, done.
remote: Counting objects: 100% (11/11), done.
remote: Compressing objects: 100% (9/9), done.
remote: Total 11 (delta 1), reused 0 (delta 0), pack-reused 0 (from 0)
Receiving objects: 100% (11/11), done.
Resolving deltas: 100% (1/1), done.
```

---

### Task 3: GitHub & THGA GitLab

1. On [GitHub](github.com), create a new empty repo under your account named `myproject-gh`.
2. On [THGA GitLab](gitlab.thga.de), create a new project named `myproject-gl`.
3. In your local repository, add these as remotes:

   ```bash
   git remote add github  git@github.com:YOUR_USERNAME/myproject-gh.git
   git remote add gitlab  git@gitlab.thga.de:YOUR_USERNAME/myproject-gl.git
   ```
4. Push your `master` branch to both `github` and `gitlab` remotes.

> Hint: You are just adding two more bare-remotes to your already existing repository!

**Your Commands & Output**

```bash
# Paste here the remote‐adding & push outputs
```

---

### Task 4: Fork, Modify, and Pull/Merge Request

1. On GitHub, **fork** one of the repos from the STEMgraph org.
2. Clone your fork locally, create a branch `pp5-changes`, and make a small change (e.g., update the README).
3. Commit and push `pp5-changes` to **your** fork, then open a **Pull Request** against the original repo.
4. Repeat on THGA GitLab: fork another students repository, clone, branch, change, push, and open a **Merge Request**. If your peers opened a merge request to your repository, review and merge or decline it!

**Your PR/MR Links & Descriptions**

* GitHub PR: *paste URL and a one-sentence summary*
* GitLab MR: *paste URL and a one-sentence summary*

---

**Remember:** Stop working after **90 minutes** and record where you stopped!
