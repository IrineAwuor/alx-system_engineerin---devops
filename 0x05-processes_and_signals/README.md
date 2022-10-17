<p> 0x05. Processes and signals

<h5> What is my PID

</p> Write a Bash script that displays its own PID.

sylvain@ubuntu$ ./0-what-is-my-pid

4120

sylvain@ubuntu$


<h5> List your processes

</P> Write a Bash script that displays a list of currently running processes.

Requirements:

Must show all processes, for all users, including those which might not have a TTY

Display in a user-oriented format

Show process hierarchy

<h5> Show your Bash PID

</p> Using your previous exercise command, write a Bash script that displays lines containing the bash word, thus allowing you to easily get the PID of your Bash process.

Requirements:

You cannot use pgrep
The third line of your script must be # shellcheck disable=SC2009 (for more info about ignoring shellcheck error here)

<h5> Show your Bash PID made easy

</p> Write a Bash script that displays the PID, along with the process name, of processes whose name contain the word bash
