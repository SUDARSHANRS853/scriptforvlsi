```
1️⃣ What is TCL? Where is it used?

Answer:

TCL (Tool Command Language) is a scripting language for automation, testing, and rapid prototyping.
Commonly used in EDA tools, log parsing, testbench scripting, and automation.
Key features: simple syntax, dynamic typing, lists/arrays, string manipulation.

2️⃣ Difference between " " and {} in TCL?

Answer:

Feature	" " (double quotes)	{} (curly braces)
Variable $a	Substituted	Literal text
Command [expr …]	Evaluated	Not evaluated
Parsing	TCL parses content	TCL takes literally

Example:

set a 5
puts "Value is $a"   ;# Output: Value is 5
puts {Value is $a}   ;# Output: Value is $a

3️⃣ How to declare variables in TCL?

Answer:

set a 10      ;# Assign integer
set b "Hello" ;# Assign string
Variables are dynamically typed
Use $ to access value: puts $a

4️⃣ How to do arithmetic in TCL?

Answer:

Use expr for calculations:
set a 5
set b 10
set sum [expr $a + $b]
puts $sum   ;# Output: 15
Increment/decrement:
incr a        ;# a = a + 1
incr a 5      ;# a = a + 5


5️⃣ Explain loops in TCL
for loop
for {set i 0} {$i < 5} {incr i} {
    puts $i
}
while loop
set i 0
while {$i < 3} {
    puts $i
    incr i
}
foreach loop
foreach x {a b c} {
    puts $x
}

6️⃣ How to write conditional statements?
set a 10
if {$a > 5} {
    puts "Greater than 5"
} elseif {$a == 5} {
    puts "Equal to 5"
} else {
    puts "Less than 5"
}
switch statement for string matching:
set color "red"
switch $color {
    "red" {puts "Stop"}
    "green" {puts "Go"}
    default {puts "Unknown"}
}

7️⃣ Explain lists in TCL
Lists are ordered collections.
set mylist [list a b c]
lappend mylist d        ;# Add element
puts [lindex $mylist 2] ;# Access element (c)
puts [llength $mylist]  ;# List length (4)

8️⃣ Explain arrays in TCL
Arrays are associative arrays (key-value pairs).
set arr(name) "Sudarshan"
puts $arr(name)          ;# Output: Sudarshan
array names arr           ;# Get all keys

9️⃣ What is a proc? Give example
proc = function in TCL
proc add {a b} {
    return [expr $a + $b]
}
puts [add 5 3]   ;# Output: 8
Local vs global:
set x 5
proc change {} {
    global x
    set x 10
}
change
puts $x    ;# Output: 10
Default argument values:
proc greet {name {greeting "Hello"}} {
    puts "$greeting, $name!"
}
greet "Sudarshan"     ;# Output: Hello, Sudarshan!


🔟 String operations
set str "Hello World"
string length $str       ;# 11
string toupper $str      ;# HELLO WORLD
string tolower $str      ;# hello world
string match "H*" $str   ;# 1 (matches pattern)

1️⃣1️⃣ File Handling
set f [open "file.txt" r]   ;# Open file for reading
set content [read $f]       ;# Read entire file
close $f
gets → read line by line
puts → write to file:
set f [open "out.txt" w]
puts $f "Hello World"
close $f

1️⃣2️⃣ Regex in TCL
regexp → match pattern
set line "Error: File not found"
if {[regexp {Error} $line]} {
    puts "Error found"
}
regsub → replace
regsub {Error} "Error: File not found" "Warning" newstr
puts $newstr   ;# Output: Warning: File not found

1️⃣3️⃣ Advanced / Automation commands
eval → execute string as TCL code
upvar → access parent scope variable
subst → perform substitution inside string

Example eval:

set cmd "set a 10"
eval $cmd
puts $a   ;# Output: 10
