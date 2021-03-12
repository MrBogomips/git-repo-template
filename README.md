# Install Hooks

## Commit Message Hook

* Copy the script `commit-msg` under the path ./git/hooks
* Grant the execution privilege to the script (chmod a+x ./git/hooks/commit-msg)

*Alternatively* you can issue the following command from a bash shell (Cygwin):

```
cd path/to/your/git/checkout \
&& install -vbm 755 <(curl -s https://gist.githubusercontent.com/dberstein/dcc50e171163c3f6e0f23b2b5de5dd49/raw/5e5372ff22a872321ad1f5469a4d579c15ce498a/commit-msg) "$(git rev-parse --git-dir)/hooks/commit-msg"
```
