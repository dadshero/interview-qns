

````markdown

---

## 1. You committed code by mistake. How will you undo the last commit but keep your changes?

👉 Use:
```bash
git reset --soft HEAD~1
````

This removes the commit but keeps the files staged, so you can commit again properly.

---

## 2. You committed code, but now you want to undo both the commit and the changes. How?

👉 Use:

```bash
git reset --hard HEAD~1
```

This removes the last commit and deletes the changes from working directory too.

---

## 3. You pushed code to the remote, but the commit message is wrong. How do you fix it?

👉 Steps:

```bash
git commit --amend -m "Correct message"
git push origin branch-name --force
```

This corrects the commit message and updates remote with force push.

---

## 4. You want to remove untracked files (not staged or committed). How will you do it safely?

👉 First check what will be deleted:

```bash
git clean -n
```

👉 Then delete them:

```bash
git clean -f
```

---

## 5. You are working on a feature, but suddenly need to switch branches without losing current work. What do you do?

👉 Use **stash**:

```bash
git stash
git checkout other-branch
```

👉 Later, bring changes back:

```bash
git stash pop
```

---

## 6. Two developers worked on the same file and Git shows a merge conflict. How do you solve it?

👉 Steps:

1. Open the file → Git will show conflict markers (`<<<<<<<`, `=======`, `>>>>>>>`).
2. Manually edit and keep the correct changes.
3. Then run:

```bash
git add file-name
git commit
```

---

## 7. You accidentally deleted a branch locally. How do you recover it?

👉 Find commit ID in reflog:

```bash
git reflog
```

👉 Create branch again:

```bash
git checkout -b branch-name commit-id
```

---

## 8. How do you see what changed between two commits?

👉 Use:

```bash
git diff commit1 commit2
```

It shows exact changes line by line between commits.

---

## 9. You need to see who modified a particular line in a file. What do you use?

👉 Use:

```bash
git blame file-name
```

It shows author and commit for each line in the file.

---

## 10. You merged a branch by mistake. How do you undo the merge?

👉 Use:

```bash
git reset --hard HEAD~1
```

This removes the merge commit.

👉 If already pushed, then:

```bash
git push origin branch-name --force
```

---


