# Commands and Scripting
## Exercises
### Print the name of all users in the system
```
awk -F':' '{print $1}' /etc/passwd
```
### Check to see if python is installed in your server, what's its version
```
command -v python &> /dev/null && python -V
```
### Find and remove all directories named "remove_me" inside /tmp
```
ls /tmp/remove_me* | xargs rm -vf
```
### How many processes named "xxx" are running in the system?
```
ps aux | grep xxx | wc -l
```
### Rename all *.txt inside a folder into *.text
```
for f in *.txt; do mv $f $(basename $f .txt).text; done
```
### Remove all files named "xxx" and contains "Shitty stuff" in /tmp
```
grep -l -e 'Shitty stuff' -f <<< ls /tmp/*xxx* | xargs rm -vf
```
### Given a http log file, print all the lines containing bad status codes (>399)
```
awk '($8 > 399)' access.log
```
### Given a http log file, find the most accessed urls, get the total number of accesses on top 5 urls
```
awk '{print $10}' access.log | sort | uniq -c | sort -n | tail -5
```