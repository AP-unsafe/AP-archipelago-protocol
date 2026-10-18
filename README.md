# Corrected Protocol File
This repo will contain the file with the corrected version of the "protocol" doc.
All corrections will be pointed out through issues or pull requests, and discussed together in class.

## How to Issue/Pull Request
To keep everything manageable and coherent with the rest, please follow these rules when submitting an Issue or a Pull Request:
- **Keep them atomic**, a PR or issue must address exactly **one** problem at a time. Avoid working continuously on a single branch of your fork, as this will stack all your unrelated modifications into a single PR.
- **Make them auto-explicative**, reviewers should understand the section, topic, and core problem just by reading the title. Use the description body to go into detail about the problem, why specific choices were made, and eventually why alternative solutions were discarded.
- **Don't separate issues and PRs**, when making a Pull Request, check if there is an issue that talks about the problem that was solved in the PR, and connect it through the developer section (on the right side) of the PR interface, this way the Issue will be marked as solved when your PR gets merged.

### How to fix stacked commits on a PR?
If you accidentally stacked multiple unrelated commits into a single pull request, you will be asked to separate them before they can be merged. You can fix this by isolating your changes into new, clean branches using git cherry-pick:

1. **Find your commit hash**: On your current working branch (the one with the stacked commits), run ```git log``` and copy the specific commit hash (e.g., ```a1b2c3d```) for the exact change you want to isolate.
2.  **Update your local main**: Switch back to your main branch and ensure it is up to date with the remote repository.
```
git checkout main
git pull
```

3. **Create a fresh branch**: Create and switch to a new branch dedicated solely to this specific fix.
```
git checkout -b fix/specific-issue-name
```

4. **Cherry-pick the commit**: Apply the isolated commit to your new branch.
```
git cherry-pick <commit-hash>
```

5. **Push and open a new PR**: Push the clean branch to your fork and open a new pull request.
```
git push origin fix/specific-issue-name
```

Repeat this process for each distinct fix you need to submit.
