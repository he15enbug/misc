# Chaining Commands

## Chaining with Semicolons

- `/challenge/pwn; /challenge/college`

## Your First Shell Script

- `echo '/challenge/pwn' > x.sh; echo '/challenge/college' >> x.sh; bash x.sh`

## Redirecting Script Output

- `echo '/challenge/pwn' > y.sh; echo '/challenge/college' >> y.sh; bash y.sh | /challenge/solve`
