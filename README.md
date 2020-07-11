# Password-Checker
This project contains a script that tests the passwords, and assigns a score to them, depending upon how strong they are.

This project we will be writing a script that will test password strength. 
The input to the script will be the path to a file which contains only the password which will be tested. 
We will test the password against multiple regex patterns to see if the password matches any of the patterns we are looking for. 
We will then add or subtract points from the password's "score" appropriately (the amount of points to add and subtract 
for each required regex check are included in the table below). 
The output will consist of only the point total for the password contained in the file specified by the input.
A password always starts with 0 points. 
The implementation for this part of the lab should be in the file pwcheck.sh. 

Password has less than 6, or more than 32 characters
Print "Error: Password length invalid."

For any valid password:
+1 point for each character in the string

If the password contains one of the following special characters (#$+%@)
+5 points

If the password contains at least one number (0-9)
+5 points

If the password contains at least one alpha character (A-Za-z)
+5 points

If the password contains a repeated alphanumeric character (i.e. aa, bbb, 55555)
-10 points

If the password contains 3 or more consecutive lowercase characters (i.e. bbb, abe, this)
-3 points

If the password contains 3 or more consecutive uppercase characters (i.e. BBB, XQR, APPLE)
-3 points

If the password contains 3 or more consecutive numbers (i.e. 55555, 1747, 123, 321)
-3 points

Unless mentioned otherwise, all point deductions and additions are one-time only per password, i.e. 
do not subtract more than 3 points if there are two occurrences of repeating lowercase characters. 
However, the same pattern may result in penalties for multiple regexes (for example, bbb results in a penalty of -13 points).

An example of the usage and output of the script is as follows:
	
$> echo ThisBlowsMindsss189 > ~/cs252/lab2-src/testfile
$> ./pwcheck.sh ~/cs252/lab2-src/testfile
Password Score: 13

As an example the password "ThisBlowsMindsss189" would receive 13 points from the following: +19 from the number of characters, 
-3 for consecutive lowercase characters, -10 for duplicate characters, +5 for a capital letter, +5 for a number, 
and -3 for consecutive numbers. 

Therefore, as shown above, the output of your program should simply be:

Password Score: 13

The output should be in a single line and should be the only output from your program. 
