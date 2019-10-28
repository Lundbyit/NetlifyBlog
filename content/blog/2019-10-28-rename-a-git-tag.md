---
title: Rename a git tag
date: 2019-10-28T17:54:07.495Z
---
I needed to rename a git tag and realised that there are no commands for that in git. To rename a tag you need to create a new tag on the commit and then delete the old one.

If you are deleting an annotated tag you might want to save the information associated with that tag.

You will need to find the commit id to tag the new commit. To find it run:

```
git log --oneline
```

Save the commit id. Then tag the commit:

```
git tag -a <new tag name> -m <message> <commitId>
```

Delete the original tag:

```
git tag -d <original tag name>
```

Push your tag to remote:

```
git push --tags
```

Delete your tag from remote:

```
git push origin :<original tag name>
```
