---
id: ab546d7a-f387-4d79-9a0e-68ee04ddf307
title: if
desc: ''
updated: 1612744832651
created: 1595536733535

---

# Synopsis

```bash
 if COMMANDS
 then
   COMMANDS
 elif COMMANDS   # optional
 then
   COMMANDS
 else            # optional
   COMMANDS
 fi              # required
 ```

# Comparison

## string comparison

```bash
[ -z STRING ]   Returns true if STRING is zero-length.
[ -n STRING ] or [ STRING ] Returns true if STRING length > zero.
[ STRING1 == STRING2 ]  Compares STRING1 to STRING2: returns true if strings are equal.
[ STRING1 != STRING2 ]  Compares STRING1 to STRING2: returns true if strings are NOT equal.
[ STRING1 < STRING2 ]   Compares STRING1 to STRING2: returns true if STRING1 is lexicographically < STRING2
[ STRING1 > STRING2 ]   Compares STRING1 to STRING2: returns true if STRING1 is lexicographically > STRING2
[ LHS [OPER] RHS ]  Compares LHS to RHS using specified operator. Returns true if expression is true
```
## num comparison
- `-eq, -ne, -lt, -le, -gt, -ge`

# Condition
- https://unix.stackexchange.com/questions/306111/what-is-the-difference-between-the-bash-operators-vs-vs-vs

### [
- [ condition ] : unix `test` command, sets exit code

### [[
- [[ cond ]]: upgraded test
    - not POSIX, not supported in `sh`

### Other
- `(( cond ))`: ksh extension that bash and zsh support
    - perform arithmetic
    - sets exit code
    - not POSIX

- (cmd): run in subshell

# Methods

## negation

```bash
if [[ $? -ne 0 ]]; then     # -ne: not equal
if ! [[ $? -eq 0 ]]; then     # -eq: equal
if [[ ! $? -eq 0 ]]; then

```

## files
- [ -e filepath ] Returns true if file exists.
- [ -d object_name ]  object_name exists as a directory.

# Examples

```bash
t1=true
if [ $t1 = true ]; then
  echo "t1 is true"
else
  echo "t1 is false"
fi

```

### Check if a file exists

```bash
[[ -s "$HOME/.profile" ]] && source "$HOME/.profile"
```