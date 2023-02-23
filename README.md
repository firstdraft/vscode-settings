# vscode-settings

Settings we recommend for student workspaces.

`ruby-project-settings.json` contains additional files to exclude from view. This is meant to provide a cleaner workspace for those Ruby projects, [like this one](https://github.com/appdev-projects/ruby-project-string-1). The file needs to be renamed `settings.json` and placed in the `.vscode/` folder in those cases.

For copying into multiple directories:

```
find *project*/.vscode/ -maxdepth 0 -exec cp vscode-settings/ruby-project-settings.json {} \;
```

(first part is directories to copy into, second part is filename)

To rename the `ruby-project-settings.json` (if that was copied as opposed to `settings.json`):

```
for file in *project*/.vscode/ruby-project-settings.json; do mv $file "$(echo $file | sed s/ruby-project-settings/settings/)"; done
```

To push the changes in many repos to github

```
for dir in *project*/; do cd $dir && git acm "update settings" && git p && cd ..; done
```
