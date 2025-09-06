

## 1️⃣ Undo last commit but keep changes
**Scenario:** You committed code by mistake.  
**Solution:**  
```bash
git reset --soft HEAD~1
````

✅ This removes the commit but keeps your files staged, so you can commit again properly.

---

## 2️⃣ Undo last commit and also remove changes

**Scenario:** You want to undo both the commit and the changes.
**Solution:**

```bash
git reset --hard HEAD~1
```

✅ This deletes the commit and also removes the changes from your working directory.

---

## 3️⃣ Fix wrong commit message after pushing

**Scenario:** You pushed code with the wrong commit message.
**Solution:**

```bash
git commit --amend -m "Correct message"
git push origin branch-name --force
```

✅ This updates the commit message and force pushes it to remote.

---

## 4️⃣ Remove untracked files safely

**Scenario:** You want to delete only untracked files.
**Solution:**

```bash
git clean -n   # shows what will be removed
git clean -f   # deletes untracked files
```

✅ First preview with `-n`, then delete with `-f`.

---

## 5️⃣ Switch branches without losing work

**Scenario:** You need to switch branches but don’t want to lose current work.
**Solution:**

```bash
git stash
git checkout other-branch
git stash pop
```

✅ `stash` saves your changes temporarily and restores them later.

---

## 6️⃣ Resolve merge conflict

**Scenario:** Two developers edited the same file, causing a conflict.
**Solution:**

1. Open the file → check conflict markers (`<<<<<<<`, `=======`, `>>>>>>>`)
2. Edit and keep the correct changes
3. Run:

```bash
git add file-name
git commit
```

✅ Conflict is resolved and changes committed.

---

## 7️⃣ Recover deleted branch

**Scenario:** You accidentally deleted a branch locally.
**Solution:**

```bash
git reflog                  # find commit ID
git checkout -b branch-name commit-id
```

✅ This recreates the branch from the last commit.

---

## 8️⃣ Compare two commits

**Scenario:** You want to see what changed between two commits.
**Solution:**

```bash
git diff commit1 commit2
```

✅ Shows line-by-line differences between the two commits.

---

## 9️⃣ Find who modified a line in a file

**Scenario:** You want to check who changed a specific line.
**Solution:**

```bash
git blame file-name
```

✅ Displays commit ID and author for each line.

---

## 🔟 Undo a wrong merge

**Scenario:** You merged a branch by mistake.
**Solution:**

```bash
git reset --hard HEAD~1
```

✅ This removes the merge commit locally.

If already pushed:

```bash
git push origin branch-name --force
```

