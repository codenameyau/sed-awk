# sed-awk

Follow the tutorials here: http://www.thegeekstuff.com/tag/sed-tips-and-tricks/

Once you've got the skills, it's time to up your game with real-life data found
in the `/data` folder. May the Tux be with you.

```bash
# Preview the files.
head data/names.csv && tail data/names.csv

# Count the number of lines.
wc data/names -l
```


### Mad Useful Commands

```bash
# List out the second column in the table.
cat text/table.txt | sed 1d | awk '{ print $2 }'

# Sum the columns in the table.
cat text/table.txt | sed 1d | awk '{ sum += $2 } END { print sum }'

# Delete blank lines.
sed '/^$/d' filename
```


### Sed Print and Delete Commands

```bash
# Print line 2.
sed -n 2p text/geek.txt

# Delete follows a similar syntax as print but without the `-n` flag.
sed 2d text/geek.txt

# Print lines `2` to `5`.
sed -n '2,5'p text/geek.txt

# Print lines `2` to the last line.
sed -n '2,$'p text/geek.txt

# Print lines starting with `3` and skipping by `2`.
sed -n '3~2'p text/geek.txt

# Prints the line matching the pattern and the next '3' lines.
sed -n '/Sysadmin/,+3p' text/geek.txt

# Prints the lines matching the between the two patterns.
sed -n '/Hardware/,/Website/p' text/geek.txt
```
