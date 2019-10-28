---
title: Docker volume mapping in windows
date: 2019-10-26T15:46:34.396Z
---
When I try to run

```
docker run -p 3000:3000 -v $(pwd):/app e6cfd18d7095
```

in powershell I get:

```
docker.exe: invalid reference format.
```

To solve it in PowerShell, use ${pwd} instead of $(pwd).

e.g

```
docker run -p 3000:3000 -v ${pwd}:\app e6cfd18d7095
```

After I ran this instruction, I got:

```
docker.exe: Error response from daemon: Drive sharing failed for an unknown reason.
```

It turns out that you also need to give docker access to your local drive.

On your tray, next to your clock, right-click on Docker, then click on Settings, there you’ll find the Shared Drives, mark your drive, and hit apply!

That solved the issue for me.
