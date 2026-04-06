1. What does grep do?
```
👉 Searches for a pattern in a file and prints matching lines.

```
🔥 2. Difference between grep and egrep?
```
👉 egrep supports extended regex (now replaced by grep -E)
```
🔥 3. What is case-insensitive search?
```
grep -i "error" file.txt
```
👉 Matches all cases (ERROR, Error, etc.)

🔥 4. How to print line numbers?
```
grep -n "error" file.txt
```
🔥 5. How to count matches?
```
grep -c "error" file.txt


👉 Counts lines, not occurrences
```
🔥 6. How to count total occurrences?
```
grep -o "error" file.txt | wc -l

```
🔥 7. How to print lines NOT matching?
```
grep -v "error" file.txt
```
🔥 8. How to search recursively?
```
grep -r "main" .
```
🔥 9. How to print only file names?
```
grep -l "error" *.txt
```
🔥 10. Difference between -l and -L?
```
-l → files with match
-L → files without match

🔥 11. What does -w do?
```
grep -w "cat" file.txt
```

👉 Matches whole word only

🔥 12. What does -o do?
```
👉 Prints only matching part, not full line
```
🔥 13. What does ^ and $ mean?
```
grep "^error" file.txt   # start of line
grep "error$" file.txt   # end of line
```
🔥 14. How to search multiple patterns?
```
grep "error\|fail" file.txt

OR

grep -E "error|fail" file.txt
```
🔥 15. What is recursive + line number?
```
grep -rn "main" .
```
🔥 16. Common Trap Question:
```
👉 Does -c count occurrences?
❌ No → counts lines only
```
🔥 17. How to ignore binary files?
```
grep -I "text" file
```
🔥 18. Real-world question:
```
👉 “Find all .c files containing main”

grep -rl "main" *.c
```
🔥 19. How to show only matching word with line number?
```
grep -on "error" file.txt
```
🔥 20. How to exclude a word and search recursively?
```
grep -rv "error" .
```
🚀 Final Interview Tip:

Combine options → that’s where real power is
Example:
```
grep -rinw "error" .

👉 Means:

-r recursive
-i ignore case
-n line number
-w whole word
```
