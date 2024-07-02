# Perceiving Permissions

## Tweaking permissions

- `chmod 200 /challenge/pwn; chmod 310 /challenge/pwn; chmod 370 /challenge/pwn; chmod 270 /challenge/pwn; chmod 770 /challenge/pwn; chmod 740 /challenge/pwn; chmod 755 /challenge/pwn; chmod 757 /challenge/pwn; chmod 777 /flag; cat /flag`
- Actually, we are expected to use `+` and `-` to add or remove permissions, e.g., `chmod u+r,g-w,o+x [FILE]`, `o` (other), `a` (all)

## Setting permissions

- Use `=`: `chmod u=rw,g=x,o=r [FILE]`
- `chmod u=x,g=rwx,o=rw /challenge/pwn; chmod u=rw,g=w,o=- /challenge/pwn; chmod u=r,g=-,o=wx /challenge/pwn; chmod u=w,g=w,o=rx /challenge/pwn; chmod u=rx,g=rwx,o=rwx /challenge/pwn; chmod u=-,g=rw,o=r /challenge/pwn; chmod u=wx,g=x,o=x /challenge/pwn; chmod u=-,g=-,o=rw /challenge/pwn; chmod 777 /flag; cat /flag`

## My dentist said I need to `chown`

- `chown [username] [file]`
- `chgrp [groupname] [file]`
- `chown hacker /flag; cat /flag`

## Why did the code feel enpowered after `chmod +x`? It got a license to thrill

- `chmod +x /challenge/getflag && /challenge/getflag`

## I tried to tell a `setuid` joke, but it escalated too quickly

```shell
$ chmod u+s /challenge/getroot && /challenge/getroot
Now you are root!
root@permissions~i-tried-to-tell-a-setuid-joke-but-it-escalated-too-q:/home/hacker/Race_Condition# cat /flag
pwn.college{*}
```
