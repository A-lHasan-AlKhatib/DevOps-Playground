# Best Practices for Branch Protection

## Summury

### Branch protection 
- This can include requiring code reviews or passing status checks.
- Protects branches from accidental bugs (untested work) or malicious changes (force pushing).

### Branch Restrection
- Restrict the teams or individuals who can push to a branch at all by enabling the option "Restrict who can push to this branch"
- This option isn't avilable for personal repository so I didn't apply it here.

### Required Status Check
- Required status checks enforce passing tests (from CI/CD systems like GitHub Actions) before merging pull requests.
- This helps prevent broken code from being merged into the main branch.
- I don't have any GitHub Actions currently in this repository, so I didn't apply it here.

### Required Pull Request Reviews
- Enable review approval before merging pull requests.
- This ensures at least one reviewer approves the changes.
- Prevents collaborators from directly merging their own pull requests.
- Pull request authors must address feedback or dismiss reviews.
- It's applied in this repository as you will see in the steps below.


## These are the steps I went through to apply for branch Protection on this repository
1. Went to repository setting -> Branches and Added new branch role
![add role](https://github.com/A-lHasan-AlKhatib/DevOps-Playground/assets/47783147/377f1929-4607-446e-91be-d1c3301f0804)

2. Set a new role and apply it only to the main, new changes will be pushed to new dev branches and will be merged to main using a PR
![set role](https://github.com/A-lHasan-AlKhatib/DevOps-Playground/assets/47783147/b60faf18-8171-4ec1-a8db-fbe65353b352)
*
![save](https://github.com/A-lHasan-AlKhatib/DevOps-Playground/assets/47783147/c1ec7c64-0a25-4c12-a018-b8a2a1afcded)


## My Current workflow to push new commits
- Create new branch (Should work if the branch was local or not, but I'll  be working with local branch): ``` git switch -c "new-dev-branch" ```

- add new changes and add them to a new commit.
- push using "-u, --set-upstream" which is used to set upstream for git pull/status: ``` git push -u origin new-dev-branch```
- On GitHub go to the new branch and create a new PR as in the example below.
![new PR](https://github.com/A-lHasan-AlKhatib/DevOps-Playground/assets/47783147/65e0d7be-3aa7-4391-b7de-70a915fe15da)
- At the end the reviewer add comments or approves the PR and it'll be merged to the main, the new branch should be deleted after merging.

## 🔗 Sources
- https://dev.to/n3wt0n/best-practices-for-branch-protection-2pe3?fbclid=IwAR0mFT6PHx_QmEaadaXCDY2WpimogMjHWHuplaRejlSLjasqWoJHEdXkntE
- https://www.youtube.com/watch?v=CNCE1gts2Yw&ab_channel=EddieJaoude
