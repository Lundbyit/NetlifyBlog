---
title: React and docker volume mapping
date: 2019-10-26T16:12:36.393Z
---
I encountered a problem when I was setting up a react dev environment.

Hot reloading is default on in create-react-app.

But it didn't seem to work when I ran the app in a docker container.

The solution to that problem was to create a .env file in the root of the project and add:

```
CHOKIDAR_USEPOLLING=true
```
