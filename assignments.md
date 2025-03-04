# Homework assignments

The course has three compulsory homework assignments. **The descrptions below are only tentative.**

The first two assignments (focusing on git) can be made optional for you if you show sufficient skills in the area, for example by having completed [PB176 Basics of Quality and Managment of Source Code](https://is.muni.cz/auth/predmet/fi/jaro2022/PB176?lang=en) (this needs to be explicitly approved by the teachers).


## 1: Single-developer scenario (deadline 6. 4.)

Prove you have elementary knowledge of git, GitHub, CI/CD systems and developer best practices.

* Setup a GitHub repository under your personal account, called `ossdev-02-${UCO}`, e.g., `ossdev-02-325219`
* Commit a small piece of code with simple functionality in `{C, C++, Java, Kotlin, Python, PHP}`. Assignment: take input two numbers `a, b`, print all primes in the interval `[a, b]`. Use algorithm of your choice (e.g., trial division, sieve). It us just a demo, not an algorithmic competition.
* Properly cover the implemented feature by tests and documentation.
* Setup a build system of your choice (makefile, cmake, gradle, ...) compiling the project (if relevant) and running the tests.
* Setup a CI/CD system (e.g. Travis, which is recommended on the GitHub).
* Setup at least one extra step as a part of the CI process (e.g. style check).
* Setup a `README.md` file for the repository and include a build or test status badge for the CI/CD results.
* Submit `repo.txt` to the IS file vault with the single line, the URL for your GitHub repository (HTTPS web view).
* Submit detailed timesheet to the IS file vault named `time.txt`, which will have separate entries for a) coding, b) implementing tests c) writing docs d) setting up project / build system / style check. 

## 2: Multi-developer scenario (deadline 30. 4.)

Prove you can use git to interact with existing reositories, resolve conflicts and adjust git history.
Create a text file `ossdev-hw-01.txt` and mark mentioned info to the file as noted below in the assignment. 
After you are done with the assignment, submit the file to the IS vault corresponding to the homework.

Setup signed commits on GitHub (generate GPG key if you don't have one, add it to GitHub, make sure your git client can sign the commit). Check some online tutorial, it is quite easy to do.

You can finish the whole assignment on your own, without need to wait for our review. We will mark it based on the git commits from the file. 

### Step 1

- Fork https://github.com/crocs-muni/open-source-development-course-hw02-1. It is a very simple Python implementation of a vector with simple operations.
- Create a new branch called `pr/step1`.
- Implement missing features marked by `# TODO`, at least 1 commit. (Find TODO in the project, e.g., `grep`).
- Implement missing tests for functions modified by you. Very simple tests will do the job. There is an example of a test already. At least 1 commit.
- Make sure Travis is passing on your newly added commits (fix the currently broken build, you can just not build for the failing version).
- Add Travis build badge to the Readme.
- Add simple info about supported operations to the Readme.
- Write down all commit IDs (hash) to the file `ossdev-hw-01.txt`. 
  - One commit ID per line, line starts with the commit ID.
  - There should be at least 2 separate commits, i.e., implementation, tests added.
  - Example: `845d5bae4a0edafb8100a311d185746abdacb58f - todo implemented` 
- Create a PR with your changes against the forked repo, PR name has to start with `[WIP] [UCO]: ` with your UCO.
- After PR is ready, imagine a reviewer tells you to add a simple python comment to the `__sub__` and to squash all the commits then. 
Before doing the squash, create a branch `pr/step1-old` that points to your current HEAD. (So we can access the old commits before the squash.)
- Do as reviewer told you, in the PR-branch `pr/step1`. Write down a commit ID to the file `ossdev-hw-01.txt`.
- Notify reviewer it's done with a PR comment, remove `[WIP]` from the PR title as your PR is approved now.
- Please, Do not look at the step 2 before finishing step 1. We want to see the conflicts! >:) 

### Step 2

Imagine something happened, 8 months passed, repository changed the maintainer and some changes to the code were made.

- Add a new remote repository to your fork: `https://github.com/crocs-muni/open-source-development-course-hw02-2`.
- Create a new branch `pr/step2` that points to your HEAD (`pr/step1`). All branches from previous steps have to stay intact.
- Rebase all your changes (`pr/step2`) on top of the `open-source-development-course-hw02-2/master`.
- Fix conflicts reasonably.
- Fix all remaining TODOs and add minor tests in a separate commit (nothing extra complicated, just some pieces of code).
- Fix unit tests, as in this PR: https://github.com/crocs-muni/open-source-development-course-hw02-2/pull/1
- Create a new PR in the `open-source-development-course-hw02-1`, the previous PR has to be left intact.
- Create a branch `pr/step2-old` that points to your HEAD. Note new commit IDs to the file.
- Same as before - squash to one commit. Add commit ID to the file.
- Add a comment to the PR saying "Done" to the step2 PR.
- Add the file with commit IDs to the PR2, as a new comment, plaintext, no attachments.

## 3: Open-source licences (deadline 14. 5.)

Prove a basic knowledge of licencing. Submit the short report in a text file `hw01.txt` to the homework vault in the information system.

* Locate the licence information of the open-source project you contribute to. Write the URL to the licence file into the report.
* Read the licence in full (or skim through it if it's long).
* Imagine you develop a product that would benefit from using this open source project. Are there any conditions you must meet if you use the open source project?  Are you then restricted in choice of a licence for your product?  Are there any additional restrictions when you sell your product? Write your reasoning into the report.
* Imagine you want to integrate the [QGIS project](https://github.com/qgis/QGIS) into the open-source project you're contributing to. Are the licenses compatible? Write your reasoning (with links to used sources, if applicable) into the report. (Note: This may be more complicated than it sounds depending on your project. Don't spend an excessive amount of time on this part.)
