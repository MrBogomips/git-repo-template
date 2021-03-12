# Install Hooks

## Commit Message Hook

* Copy the script `commit-msg` under the path ./git/hooks
* Grant the execution privilege to the script (chmod a+x ./git/hooks/commit-msg)

*Alternatively* you can issue the following command from a bash shell (Cygwin):

```
cd path/to/your/git/checkout \
&& install -vbm 755 <(curl -s https://git.nexusat.it/giovanni.costagliola/git-repo-template/raw/main/commit-msg) "$(git rev-parse --git-dir)/hooks/commit-msg"
```
