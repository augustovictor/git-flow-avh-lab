# Git flow avg Lab

## Instalation and initialization
[Installation and tutorial](https://danielkummer.github.io/git-flow-cheatsheet/index.html)

Enter the repository and do `git flow init`

## Commands
### Feature
**All feature branches should follow the structure: `<task-name>-<branch-name>`. E.g., `1-page-title`**

Command | Description
--------|------------
`git flow feature start <branch>` | Creates a new feature branch from `develop`
`git flow feature finish <branch>` | Merge branch to `develop` and delete local and remote
`git flow feature publish <branch>` | Publish the branch so other people can view/work on it as well
`git flow feature pull origin <branch>` | Pull a published feature branch
`git flow feature track <branch>` | Track a feature branch

### Bugfix
Command | Description
--------|------------

### Release
Command | Description
--------|------------
`git flow release start <branch> [ BASE sha-1 ]` | Creates a release branch from develop
`git flow release finish <branch>` | Finish a release branch
`git push --tags` | Push tags

### Hotfix
**The `<version>` will be always the release branch version to be fixed without the 'release' name**
Command | Description
--------|------------
`git flow hotfix start <version> [BASENAME]` | Creates a hotfix branch from `master`

### Support
Command | Description
--------|------------

## Examples
- Feature branch
    - `git flow feature start 1-page-title`
    - Merge feature branch into develop
        - `git flow feature finish 1-page-title`
- Release branch
    - `git flow release start sprint1-release`
    - Finish a release
        - `git flow release finish sprint1-release`
- Hotfix branch
    - `git flow hotfix start page-title`
    - Finish a hotfix
        - `git flow hotfix finish page-title`
    

## Observations
- Feature branches are created from `develop`;
- If you're working on a feature that other people will also have to work on it then you should publish the branch.;
- A release branch can be created from a specific commit by providing its sha-1;
    - REMEMBER TO PUSH TAGS AFTER RELEASING THE BRANCH;
    - `git push --tags`;
- Hotfixes are urgend fixes that have to be done to production code. So they are branched from `master` and merged back to it;
    - Commit and push changes
    - Finish the hotfix branch
    - Push tags

## Best practices
- Publish the release branch once it's created. So other developers can work on it if necessary;