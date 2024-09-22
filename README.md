//Ross Kane

Overview
This Unix Toolkit is a custom-built command-line interface designed to enhance productivity in Unix environments. It leverages fundamental Unix system calls and concepts to provide a robust and flexible toolset for developers and system administrators.

Features
Process Management: Utilizes fork() and execvp() to create and manage processes.
Piping: Implements inter-process communication through piping.
Signal Handling: ctrl-z SIGSTP signal handling
Input/Output Redirection: Uses file descriptors to handle input and output redirection seamlessly.
Custom Commands: Includes custom implementations of common Unix commands such as mypwd and mycd.
Technical Details
Language: C/C++
System Calls: fork(), execvp(), pipe(), dup2()
Special commands: 
- mypwd: Prints current working directory
- mycd: Works like cd unix command
- myexit: Exits the Program


Developers Notes on mytoolkit.x
		
	-Do not redirect file for execution as this causes an infinite ooop
	
	-Commands must be typed individually, I am unsure why this is the case, maybe due to lack of control d signal handling	

	-Does not have control-d signal handling working
	
	-Executables such as a.out or one called test MUST need ./a.out or ./test in order to function properly but they work as intended! 

	-Single piping is it's own case and then multiple pipes are able to be supported after. I would max test 4 but it is capable of more

	-The following works for input/output redirection:  command1 < test1.txt     command1 > test1.txt   command1 < test1.txt > test2.txt
		No other i/0 style redirection was meant to be implemented and this is what we have

	- PLEASE MAKE SURE ALL COMMANDS ARE SEPERATED BY A SPACE  such as: command1 -args   or in cases of piping: ls | sort | wc or I/0 redirect: command1 > test.txt

	-I decided to use fork/execvp for this program because I deemed it rather practical to simply create the new processes and run them inside my program rather than creating brand new external ones. I do not have the most experience with forking/execvp and this project was a super useful workshop in figuring out how to use them. That is is why i chose to do my special commands: mycd, mypwd and myexit this way.




