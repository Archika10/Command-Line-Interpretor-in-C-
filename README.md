# Command-Shell-Implementation-in-CPP-

This program simulates the working of command line interface in Unix-like environment. Implemented Functionalities are as under:
1. Execute all the External commands (ls, clear, vi etc.)
2. Implement Internal commands: cd, pwd
3. Initialize and use environment variables
4. Print environment variables using echo command
5. Redirection operators: STDIN, STDOUT, STDERR (>>,>,<<,<,2>) 
6. Support for history command and '!' operator (history, !!, !-1, !10,!-10 etc)
7. Pipes “|” (multiple) (Ex: ls | grep 'a' | wc)


## Implementation Details:-

The file.cpp contains the main function which takes the input from user and checks it for pipeline. 
If pipeline exist it processes the data separately else it passes the data to the functions. 

int startprocess(char arr[], int i):<br />
This function is defined for checking the REDIRECTIONS. It passes the processed output to function process

int process(char arr[]):<br />
This function does the major part of the program. It tokenizes and checks for various possibilities of commands. The types of commands that are checked here:
1) Internal commands: pwd and cd
2) echo commands
3) setting and getting environment variables
4) history
5) ! : (i) !number (ii) !string (iii) !!
6) External commands

void phist():<br />
Prints the history text file on the STDIN

void writehist(char arr[]):<br />
checks whether the threshold is crossed or not in the text file. If it is than rotates and shifts the data. And then write the character array which is input to the function in the text file.

int check(char c):<br />
This functions takes a char as input and checks whether its a digit or +/-. Returns 1 if it is , else return -1
