---
date: 2024-09-20 03:41 +0530
layout: page
tags: [ tips, linux ]
---

# Tips #



[Search for executable files using find command](https://stackoverflow.com/questions/4458120/search-for-executable-files-using-find-command), answered by GreenGiant - Stack Overflow](https://stackoverflow.com/users/539048/greengiant)

On GNU versions of find you can use `-executable`:

``` shell
find . -type f -executable -print
```

For BSD (and MacOS) versions of find, you can use `-perm` with `+` and an octal mask:

``` shell
find . -type f -perm +111 -print
```

In this context "+" means "any of these bits are set" and 111 is the execute bits. Note that this is not identical to the `-executable` predicate in GNU find. In particular, `-executable` tests that the file can be executed by the current user, while `-perm +111` just tests if any execute permissions are set.