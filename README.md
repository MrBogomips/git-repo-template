# Nexus Git Standard Hooks

A set of standard hooks designed to improve DevOps Experience by:
* Enabling JIRA Integration
* Enabling CI/CD semantic messages
* Promoting best-bractice

## Commit Message Hook

*This hook validate the format of the commit message.*

### USAGE and SYNTAX

The commit message MUST honour one of the following patterns:
* a *conventional commit message* subject (to be parsed into changelogs, see (https://www.conventionalcommits.org/en/v1.0.0) ):
   - a change type, either of "build", "chore", "ci", "docs", "feat", "fix", "perf", "refactor", "revert", "style", "test" or "Publish"
   - optionally, in parenthesis, subsystem(s) affected by the change (comma delimited list)
   - a colon, space (": ") and a brief subject (60 characters maximum) not ending with a period
   - a space and in parenthesis, a csv of JIRA issue id " (NEXUS-123)" OR " (NEXUS-123,NEXUS-456)"... or the tags "[skip ci]" or "[ci]" (do we use these?)
* ... or, a Git autosquash line, i.e. "fixup! My previous commit" or "squash! Another previous commit" (see https://thoughtbot.com/blog/autosquashing-git-commits )
* ... or, a merge commit "Merge branch x..."
* ... or, a work-in-progress tag "WIP: "
* optionally (not validated), two line breaks and a commit message body

### EXAMPLES of valid commit messages

* `feat: new button (NEXUS-1)`
* `feat(UI/UX): new button (1,2,3)`
* `fix(ComponentA, ComponentB): new button (NEXUS-1,NEXUS-2)`
* `docs: README.me improved (NEXUS-1)`
* `refactor: Main.cs (1)`
* `Publish: Main deploy (NEXUS-1)`
* `WIP: still working`
* `fixup! my previous commit (See note above!!!)`
* `squash! another previous commit (See note above!!!)`

### Install procedure

* Copy the script `commit-msg` under the path ./git/hooks
* Grant the execution privilege to the script (chmod a+x ./git/hooks/commit-msg)

*Alternatively* you can issue the following command from a linux/unix shell (or Windows/Cygwin):

### Bash install one-liner 

```
cd path/to/your/git-repo

install -vbm 755 <(curl -s https://git.nexusat.it/giovanni.costagliola/git-repo-template/raw/main/commit-msg) "$(git rev-parse --git-dir)/hooks/commit-msg"
```

### Zsh install one-liner 

```
cd path/to/your/git-repo

install -vbm 755 =(curl -s https://git.nexusat.it/giovanni.costagliola/git-repo-template/raw/main/commit-msg) "$(git rev-parse --git-dir)/hooks/commit-msg"
```