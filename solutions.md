Bandit game

# Level 0

`ssh -p 2220 bandit0@bandit.labs.overthewire.org`

# Level 1

`cat readme`

Note that I got scared and did `file` just to check. Not that thats sufficient
to be safe

# Level 2

`cat ./-`.

`-` in bash is a character that means `stdout` for SOME operations. eg
`echo "whatever" | cat -`

# Level 3

`cat ./--spaces\ in\ this\ filename-- ` or `cat "./--spaces in this filename--"`

# Level 4

```bash
bandit3@bandit:~$ la inhere/
...Hiding-From-You
bandit3@bandit:~$ cat inhere/...Hiding-From-You
```

# Level 5

```bash
bandit4@bandit:~$ file inhere/*
inhere/-file00: data
inhere/-file01: data
inhere/-file02: data
inhere/-file03: data
inhere/-file04: data
inhere/-file05: data
inhere/-file06: data
inhere/-file07: ASCII text
inhere/-file08: data
inhere/-file09: data
bandit4@bandit:~$ cat inhere/-file07
```

# Level 6

```bash
bandit5@bandit:~$ find . -type f -size 1033c ! -executable
./inhere/maybehere07/.file2
bandit5@bandit:~$ find . -type f -size 1033c ! -executable -exec file {} +
./inhere/maybehere07/.file2: ASCII text, with very long lines (1000)
```

# Level 7

```bash
bandit6@bandit:~$ find / -type f -size 33c -user bandit7 -group bandit6 2>/dev/null
/var/lib/dpkg/info/bandit7.password
bandit6@bandit:~$ find / -type f -size 33c -user bandit7 -group bandit6 -exec cat {} + 2>/dev/null
```

# Level 8

```bash
bandit7@bandit:~$ grep "millionth" data.txt
```

# Level 9

```bash
bandit8@bandit:~$ sort data.txt | uniq -u
```

# Level 10

```bash
bandit9@bandit:~$ strings data.txt | grep "==="
========== the
2========== password
========== is
```
