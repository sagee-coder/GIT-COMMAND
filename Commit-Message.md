# Change a Previous Git Commit Message

### Setp 1: View all commits

```bash
git log --oneline
```

### Step 2: Start an interactive rebase

- Decide how many commits back you want to edit. For example, to edit the 2nd-last commit:

```bash
git rebase -i HEAD~2
```

### Step 3: Edit the commit message

- Git will open your default editor (usually Vim).
- Find the commit you want to change.
- Replace `pick` with `reword` (or `r`) only for the commit whose message you want to change.
- Save and exit the editor: `Esc + :wq`

### Step 4: Enter the new commit message

- Git will open the editor again for the commit message.
- Update the message, then save and exit: `Esc + :wq`

### Step 5: Push the updated commit to GitHub

- Because rewriting a commit changes its hash, you need to force push:

```bash
git push origin main --force
```

Now the commit message is updated on GitHub, and your local branch remains up-to-date.
