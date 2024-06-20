# Processes and Jobs

## Listing Processes

- `ps` either stands for "process snapshot" or "process status", and it lists processes. By default, ps just lists the processes running in our terminal, which honestly isn't very useful
    
    ```shell
    $ ps
    PID TTY          TIME CMD
    329 pts/0    00:00:00 bash
    349 pts/0    00:00:00 ps

    PID: process identifier
    TTY: the terminal on which the commands are running (in this case, the designation pts/0)
    TIME: the total amount of cpu time that the process has eaten up so far
    ```

- As `ps` is a very old utility, its usage is a bit of a mess. There are two ways to specify arguments
    - **"Standard" Syntax**: in this syntax, we can use `-e` to list "every" process and `-f` for a "full format" output, including arguments. These can be combined into a single argument `-ef`.

    - **"BSD" Syntax**: in this syntax, we can use `a` to list processes for all users, `x` to list processes that aren't running in a terminal, and `u` for a "user-readable" output. These can be combined into a single argument `aux`.

    - These two methods, `ps -ef` and `ps aux` result in slightly different, but cross-recognizable output.

    - `ps -ef` additionally outputs the Parent Process ID (PPID), which is the PID of the process that launched the one in question, while `ps aux` outputs the percentage of total system CPU and Memory that the process is utilizing

- Solution

    ```shell
    $ ps aux | grep challenge
    root          49  0.0  0.0   4204  3192 ?        S    03:25   0:00 /challenge/15241-run-19359
    hacker       883  0.0  0.0   3304   656 pts/0    S+   03:27   0:00 grep --color=auto challenge
    $ /challenge/15241-run-19359
    Yahaha, you found me! Here is your flag:
    pwn.college{IryoGtC24hCYZmoZ6LLCZsjYTEQ.dhzM4QDL2kzM4QzW}
    Now I will sleep for a while (so that you could find me with 'ps').
    ```

## Killing Processes

- Kill the process of `/challenge/dont_run` before running `/challenge/run`

    ```shell
    $ ps aux | grep dont_run
    hacker        64  0.0  0.0   4124  3000 ?        Ss   05:48   0:00 /challenge/dont_run
    hacker       473  0.0  0.0   3304   720 pts/0    S+   05:48   0:00 grep --color=auto dont_run
    $ kill 64 && /challenge/run
    Great job! Here is your payment:
    pwn.college{*}
    ```

## Interrupting Processes

## Suspending Processes

## Resuming Processes

## Backgrounding Processes

## Foregrounding Processes

## Starting Backgrounded Processes