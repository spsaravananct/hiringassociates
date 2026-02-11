# Create phase1 branch and keep main as backup

Run these commands on your **AWS server** (SSH: `root@ip-172-31-28-66`).

## 1. Go to project and check status

```bash
cd /var/www/html/hiringassociates_com
git status
```

## 2. Create branch `phase1` and put your changes there

```bash
# Create and switch to new branch phase1
git checkout -b phase1

# Stage all your changes
git add .

# Commit (use your own message if you like)
git commit -m "Phase 1 changes"

# Push phase1 to GitHub (main is not touched)
git push -u origin phase1
```

## 3. Result

- **main** on GitHub = unchanged (backup).
- **phase1** on GitHub = your current files with changes.
- On AWS you are now on **phase1**.

## 4. Later: pull updates on AWS

- To get latest **phase1** (your working branch):
  ```bash
  git checkout phase1
  git pull origin phase1
  ```

- To switch back to **main** (backup):
  ```bash
  git checkout main
  git pull origin main
  ```

## If you get "nothing to commit"

Your working tree is clean. Then you can still create the branch and push (main and phase1 will be the same until you make more changes):

```bash
git checkout -b phase1
git push -u origin phase1
```

Then switch back to main on the server if you want to serve the backup version:

```bash
git checkout main
```
