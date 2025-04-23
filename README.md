# My-First-Repo
Exactly what the name suggests
<br>
Author- Anon Ymous
Aim 1: Clone, Create, Commit, and Push to Remote

Question:

1. Clone a remote Git repository to your local system.

2. Create a new branch named feature-branch and switch to it.

3. Create a new file, newfile.txt, and add some content to it.

4. Stage and commit the changes with an appropriate commit message.

5. Push the feature-branch to the remote repository (GitHub).

git clone https://github.com/username/repository-name.git

cd repository-name

git checkout -b feature-branch

echo "This is a new file for the feature branch." > newfile.txt

git add newfile.txt

git commit -m "Add newfile.txt with initial content"

git push origin feature-branch

Aim 2: Create and Merge Branches

Question:

1. Clone a repository and create a new branch named my-feature.

2. Make a small change in an existing file (e.g., README.md) on the my-feature

branch.

3. Stage and commit your changes.

4. Merge the my-feature branch into the main branch locally after reviewing the

changes.

git clone https://github.com/username/repository-name.git

cd repository-name

git checkout -b my-feature

echo "This is a new line added in my-feature branch." >> README.md

git add README.md

git commit -m "Update README.md with a new line in my-feature branch"

git checkout main

git merge my-feature

Aim 3: Revert a Commit

Question:

1. Clone the repository and make several commits (at least 3).

2. Revert a specific commit from your commit history without removing history (use git revert).

3. Verify the revert and ensure a new commit is created that undoes the changes.

git clone https://github.com/username/repository-name.git

cd repository-name

# Make 3 commits

echo "First commit" > file1.txt

git add file1.txt

git commit -m "Add file1.txt"

echo "Second commit line" >> file1.txt

git add file1.txt

git commit -m "Append second line to file1.txt"

echo "Third commit file" > file2.txt

git add file2.txt

git commit -m "Add file2.txt"

# View history and revert a commit

git log

git revert <commit-hash>

Let’s say you want to revert the second commit (message: Append second line to file1.txt).

Copy its hash (e.g., e4f5g6h) and run:

bash

CopyEdit

git revert e4f5g6h

This does not delete history — it creates a new commit that undoes the

changes.

Aim 4: Modify a Commit Message (Amend Last Commit)

Question:

1. Clone a repository and make a commit with an initial message.

2. Amend the commit message to correct any mistakes or improve the message.

3. Verify the changes by checking the commit history.

git clone https://github.com/username/repository-name.git

cd repository-name

echo "Initial content" > file.txt

git add file.txt

git commit -m "Intial msg for file" # Step 1 commit

git commit --amend -m "Corrected message for file.txt" # Step 2 amend

git log --oneline # Step 3 verify

Aim 5: Stash, Apply, and Pop Changes

Question:

1. Clone the repository and make uncommitted changes to an existing file.

2. Stash these changes temporarily.

3. Switch to a different branch and later return to the original branch.

4. Apply the stashed changes and commit them.

git clone https://github.com/username/repository-name.git

cd repository-name

echo "Temporary edit in README.md" >> README.md

git status

git stash

git checkout -b temp-branch

git checkout main

git stash pop # or use `git stash apply` if you want to keep it in stash

git add README.md

git commit -m "Apply stashed changes to README.md"

Aim 6: Resolve Merge Conflicts

Question:

1. Clone the repository and create two branches, branch-1 and branch-2.

2. Modify the same lines in the same file on both branches to create a conflict.

3. Attempt to merge branch-2 into branch-1 and resolve the conflict manually.

4. Commit the resolved file and verify the successful merge.

git clone https://github.com/username/repository-name.git

cd repository-name

git checkout -b branch-1

echo "This is a sample file." > conflict.txt

git add conflict.txt

git commit -m "Add conflict.txt in branch-1"

git checkout -b branch-2

echo "Change from branch-2" > conflict.txt

git add conflict.txt

git commit -m "Edit conflict.txt in branch-2"

git checkout branch-1

echo "Change from branch-1" > conflict.txt

git add conflict.txt

git commit -m "Edit conflict.txt in branch-1"

git merge branch-2 # triggers conflict

# Resolve conflict manually in conflict.txt

git add conflict.txt

git commit -m "Resolve merge conflict in conflict.txt"

git clone https://github.com/username/repository-name.git

cd repository-name

git checkout -b branch-1

echo "This is a sample file." > conflict.txt

git add conflict.txt

git commit -m "Add conflict.txt in branch-1"

git checkout -b branch-2

echo "Change from branch-2" > conflict.txt

git add conflict.txt

git commit -m "Edit conflict.txt in branch-2"

git checkout branch-1

echo "Change from branch-1" > conflict.txt

git add conflict.txt

git commit -m "Edit conflict.txt in branch-1"

git merge branch-2 # triggers conflict

# Resolve conflict manually in conflict.txt

git add conflict.txt

git commit -m "Resolve merge conflict in conflict.txt"

Aim 7: Work with Git Submodules

Question:

1. Clone a repository with submodules.

2. Initialize and update the submodules.

3. Modify a file in one of the submodules and commit the change.

4. Commit the changes to the main repository and verify that the submodule changes

are

reflected.

git clone --recurse-submodules https://github.com/username/repository-name.git
cd repository-name
# Or if cloned without recurse
git submodule init
git submodule update
cd submodule-directory
echo "Submodule edit" >> subfile.txt
git add subfile.txt
git commit -m "Update subfile.txt in submodule"
cd ..
git add submodule-directory
git commit -m "Update submodule pointer after changes"
Aim 8: Cherry-pick a Commit
Question:
1. Clone the repository and make several commits on a different branch (e.g., feature-
branch).
2. Identify a commit you want to cherry-pick from feature-branch to the main branch.
3. Use git cherry-pick to bring that commit to the main branch and commit the
changes.
git clone https://github.com/username/repository-name.git
cd repository-name
git checkout -b feature-branch
echo "First commit" > file1.txt
git add file1.txt
git commit -m "Add file1.txt with first commit"
echo "Second commit" > file2.txt
git add file2.txt
git commit -m "Add file2.txt with second commit"
echo "Third commit" > file3.txt
git add file3.txt
git commit -m "Add file3.txt with third commit"
git log --oneline # Note the commit hash you want
git checkout main
git cherry-pick <commit-hash>

