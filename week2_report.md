\# Git Homework - Week 2 Report



\## PART A: Branching, Commits, and 3-way Merge

1\. \*\*Create and commit week2.md on branch week2:\*\*

&#x20;  - Commands used:

&#x20;    ```bash

&#x20;    echo "Week 2 initial content" > week2.md

&#x20;    git add week2.md

&#x20;    git commit -m "Add week2.md file"

&#x20;    git checkout -b week2

&#x20;    ```

2\. \*\*Make 2 commits on branch week2:\*\*

&#x20;  - Commands used:

&#x20;    ```bash

&#x20;    echo "Work 1" >> week2.md

&#x20;    git commit -am "working 1"

&#x20;    echo "Work 2" >> week2.md

&#x20;    git commit -am "working 2"

&#x20;    ```

3\. \*\*Add text, switch to master, and document findings:\*\*

&#x20;  - Commands used:

&#x20;    ```bash

&#x20;    echo "Extra work on week2" >> week2.md

&#x20;    git commit -am "Add extra text in week2"

&#x20;    git checkout master

&#x20;    ```

&#x20;  - \*\*Findings about week2.md:\*\* The content of `week2.md` in the working directory changes depending on which branch is currently checked out. Changes made on the `week2` branch are isolated until merged.

4\. \*\*Create week2b in 1 command, 3-way merge with week2, and delete week2:\*\*

&#x20;  - Commands used:

&#x20;    ```bash

&#x20;    git checkout -b week2b

&#x20;    git merge week2

&#x20;    git branch -d week2

&#x20;    ```



\---



\## PART B: Branch Filtering and Renaming

1\. \*\*Create wip branch, add wip.txt, commit, and merge to master:\*\*

&#x20;  - Commands used:

&#x20;    ```bash

&#x20;    git checkout -b wip

&#x20;    echo "Work in progress content" > wip.txt

&#x20;    git add wip.txt

&#x20;    git commit -m "Add wip.txt"

&#x20;    git checkout master

&#x20;    git merge wip

&#x20;    ```

2\. \*\*Filter branches (Merged vs. No-merged):\*\*

&#x20;  - Merged branches:

&#x20;    ```bash

&#x20;    git branch --merged

&#x20;    ```

&#x20;  - Unmerged branches:

&#x20;    ```bash

&#x20;    git branch --no-merged

&#x20;    ```

3\. \*\*Delete week2b branch:\*\*

&#x20;  - Command used:

&#x20;    ```cmd

&#x20;    git branch -d week2b

&#x20;    ```

4\. \*\*Rename wip to work-in-progress and publish to GitHub:\*\*

&#x20;  - Commands used:

&#x20;    ```bash

&#x20;    git checkout wip

&#x20;    git branch -m work-in-progress

&#x20;    git push -u origin work-in-progress

&#x20;    ```



\---



\## PART C: Upstream Tracking and Pull Requests

1\. \*\*Update wip.txt on work-in-progress branch and commit:\*\*

&#x20;  - Commands used:

&#x20;    ```bash

&#x20;    git checkout work-in-progress

&#x20;    echo "More update on wip" >> wip.txt

&#x20;    git commit -am "Update wip.txt"

&#x20;    git push

&#x20;    ```

2\. \*\*Command to view upstream remote branches and ahead/behind counts:\*\*

&#x20;  - Command used:

&#x20;    ```bash

&#x20;    git branch -vv

&#x20;    ```

3\. \*\*Pull Request:\*\*

&#x20;  - Opened a pull request from `work-in-progress` into `master`/`main` via GitHub Web UI.



\---



\## PART D: Rebase and Fast-forward Merge

1\. \*\*Create experiment branch from master and make 2 commits:\*\*

&#x20;  - Commands used:

&#x20;    ```bash

&#x20;    git checkout master

&#x20;    git checkout -b experiment

&#x20;    echo "Exp file 1" > exp1.txt

&#x20;    git add exp1.txt

&#x20;    git commit -m "Add exp1"

&#x20;    echo "Exp file 2" > exp2.txt

&#x20;    git add exp2.txt

&#x20;    git commit -m "Add exp2"

&#x20;    ```

2\. \*\*Switch to master and make 1 commit:\*\*

&#x20;  - Commands used:

&#x20;    ```bash

&#x20;    git checkout master

&#x20;    echo "Master update" > master\_file.txt

&#x20;    git add master\_file.txt

&#x20;    git commit -m "Add master file"

&#x20;    ```

3\. \*\*Rebase experiment into master \& Explanation:\*\*

&#x20;  - Commands used:

&#x20;    ```bash

&#x20;    git checkout experiment

&#x20;    git rebase master

&#x20;    ```

&#x20;  - \*\*Explanation of what happened:\*\* Rebase moves the base of the `experiment` branch to the current tip of `master`, replaying its commits one by one on top of the latest master commits to create a linear history.

4\. \*\*Fast-forward merge and push:\*\*

&#x20;  - Commands used:

&#x20;    ```bash

&#x20;    git checkout main

&#x20;    git merge experiment

&#x20;    git push origin main

&#x20;    ```

