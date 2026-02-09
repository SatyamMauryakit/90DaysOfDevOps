Day 06 – File Read & Write Practice

🔹 Step 1 – Create file
touch notes.txt

Creates an empty file called notes.txt.

🔹 Step 2 – Write first line (overwrite)
echo "Learning Linux file IO" > notes.txt
Writes line into file. If file already exists, it replaces content.


🔹 Step 3 – Append second line
echo "Using redirection operators" >> notes.txt

Adds new line without removing previous content.
 🔹 Step 4 – Append using tee
echo "tee writes and displays output" | tee -a notes.txt

Shows text on screen and appends to file.

🔹 Step 5 – View full file
cat notes.txt
Learning Linux file IO
Using redirection operators
tee writes and displays output

Displays entire file.

🔹 Step 6 – View first 2 lines
head -n 2 notes.txt
Shows first two lines.

🔹 Step 7 – View last 2 lines
tail -n 2 notes.txt
Shows last two lines.

📄 Sample Content of notes.txt
Learning Linux file IO
Using redirection operators
tee writes and displays output

🧠 What I Learned

> overwrites file

>> appends file

tee writes + prints

cat, head, tail help read files



