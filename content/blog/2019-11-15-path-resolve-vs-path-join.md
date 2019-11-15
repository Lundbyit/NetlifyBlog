---
title: Path.resolve vs Path.join
date: 2019-11-15T20:55:58.758Z
---
Path is a module that I see in a lot of js-tutorials.

Sometimes .resolve is used and sometimes .join is used.

I took a while until I understood what the difference were.

Join only joins path together. While resolve returns a absolute path.

e.g

```
path.resolve('/path', '/path2'); // returns '/path2'
```

```
path.join('/path', '/path2'); //returns '/path/path2'
```

https://nodejs.org/docs/latest/api/path.html
