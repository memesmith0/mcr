#!/bin/sh
mcr(){ while read -r i; do eval "$( printf "%s" "$i" | awk "$1" ; )" ; done ; } ;

#mcr is a mcro system intended for use in posix compliant shell environments
#it has a very simple proceess similar to a repl or a read eval print loop.
#a repl is a name for a shell or a terminal or a command prompt or code window.
#it stand for read eval print loop.
#(loop (print (eval (read)))) is the structure by which a repl normally works.
#first information is read from the user or from the computer.
#second of all this informated is treated as computer code and used as code
#that code if it has an output is displayed on the screen via printing.
#finally, the program loops back to the beginning of its program.
#when the loop loops back the read process is started all over again.
#then the evaluation process is started over again
#the value which was read is once again treated as code
#the output of that code is once again displayed on the screen
#and yet again the program loops to its start and so on
#it keeps doing this until it reads an exit command and that exit command gets evaluated
#this is a very similar system which does the following: (loop (print (eval (macro (read)))))
#here another layer is added between the code that is read from the user and the machine itself
#this layer edits the code that is read into the program before that code gets run
#by aditing the code in arbitrary ways this essentially allows the user to invent new langauges.
#the editor in this instance is a program called awk and a new instance of awk is run once per line.
#this is a very slow and inefficient process
#mcr can speed up this process by being used to help automate the process of developing more efficient code.
#the ordinary shell code a novice would write with mcr might be grossly inefficient
#proper use of mcr by a master would be more optimized because the code that mcr is told to generate can eb more optimal.
#usage: mcr '{ print "printf \"\%s\" \"%s\", $0 }' should be a rough approximation of gnu cat
