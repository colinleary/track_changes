## Step 1

Download a complete copy of the original latex code (all files, images, etc). Then make the required changes and download the updated files as well. Store these in their own directories. 

## Step 2
 
Grab the file and unzip it. It is a perl script, so if you don't have perl installed you will need to figure that out.

http://mirrors.ctan.org/support/latexdiff.zip

## Step 3

Grab the executable from the latexdiff directory, it is called latexdiff.

## Step 4

The --flatten flag tells the latexdiff script to resolve \input{} and \include{} commands in the latex code. This is essential if you have a main file that references other latex files. The code syntax is:

./latexdiff --flatten old_dir/main.tex new_dir/main.tex > output.tex

## Step 5

The output file will contain all the necessary bits to compile the entire document. If you place the output file, and the figures in a directory and try to compile, you should be all set.

It's important to note that some things do not play well with the track changes. If you make a change inside a table, this is likely to cause errors. When the errors pop up, there will likely be many dozen reported. Just fix the first and that usually is all you need.

I have included my project, the old, new, track_changes_broken and track_changes_fixed so you can see what to expect, and an example of errors that popped up and how I fixed them. Look at line 205 of the main code in track_changes_broken. The change made was removing a tilde (~) and replacing it with $\sim$. For some reason this did not compile, and so to fix that we just got rid of the track changes bits for that correction. See line 205 in the main file in track_changes_fixed.