# Shell Variables

## Learn to print out variables!

- `echo $FLAG`

## Printing out variables without echo!

- `env | grep FLAG`

## Learn to set variables!

- `PWN=COLLEGE && /challenge/run`

## Learn to set multi-word variables!

- `PWN="COLLEGE YEAH" && /challenge/run`

## Learn to export variables into child processes!

- `PWN=COLLEGE && export PWN && COLLEGE=PWN && /challenge/run` didn't work, I still don't know why
    ```shell
    $ PWN=COLLEGE && export PWN && COLLEGE=PWN && /challenge/run
    Incorrect...
    You have not set the COLLEGE variable to the correct value (it should be 
    'PWN'). Do that before running this script! Even though it is not exported, in 
    this challenge, we have ways to check...
    You've set the PWN variable to the proper value!
    You've set the COLLEGE variable to the proper value!
    ```
- Solution: Run `PWN=COLLEGE && COLLEGE=PWN && export PWN`, then run `/challenge/run`

## Setting variables with `read`

- Run `read PWN`, then type `COLLEGE`

## Reading files with `read`

- `read PWN < /challenge/read_me`
