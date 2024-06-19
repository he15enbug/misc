# Piping

## Redirecting output

- `echo PWN > COLLEGE`

## Redirecting more output

- `/challenge/run > ./myflag && cat ./myflag`

## Appending output

- `/challenge/run >> the-flag && cat the-flag`

## Redirecting errors

- `command > file` is actually equivalent to `command 1> file`, which redirects the standard output (FD is 1) to the file, we can also redirect the standard error using `2>`
- `/challenge/run > myflag 2> instructions && cat myflag`

## Redirecting input

- Use `<` to redirect input
- `echo COLLEGE > PWN && /challenge/run < PWN`

## Grepping stored results

- `/challenge/run > /tmp/data.txt && grep pwn.college /tmp/data.txt`

## Grepping live output

- We can use this using the `|` (pipe) operator. Standard output from the command to the left of the pipe will be connected to (piped into) the standard input of the command to the right of the pipe
- `/challenge/run | grep pwn`

## Grepping errors

- The `|` operator redirects only standard output to another program, and there is no `2|` form of the operator! It can *only* redirect standard output (file descriptor 1)
- The shell has a `>&` operator, which redirects a file descriptor to *another* file descriptor, e.g., `2>&1` redirects the standard error to standard output
- `/challenge/run 2>&1 | grep pwn`

## Duplicating piped data with tee

- The `tee` command, named after a "T-splitter" from *plumbing* pipes, duplicates data flowing through your pipes to any number of files provided on the command line
- Solution
    ```shell
    $ /challenge/pwn | tee log | /challenge/college
    $ cat log
    Usage: /challenge/pwn --secret [SECRET_ARG]

    SECRET_ARG should be "49ByxggF"
    $ /challenge/pwn --secret 49ByxggF | /challenge/college
    Processing...
    Correct! Passing secret value to /challenge/college...
    Great job! Here is your flag:
    pwn.college{*}
    ```
