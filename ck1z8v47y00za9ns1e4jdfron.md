## MySQL Administration - Export via Command Line

MySQL is a very famous open source RDBMS having been used in the applications with the support to several different programming languages (Java, PHP etc.,).  Apart from the SQL commands execution in the terminal and from the APIs (JDBC for Java, PDO for PHP), we should also be familiar with the minimal administrative commands. 

One such popular activity is to take the backup of the database (**export**) for any future references. There are several GUIs to help you achieve it quickly. However being a programmer we should be familiar on the actual command being invoked on the back end, so that we can get it automated and even schedule it to get it executed at regular intervals. 

I have been used to do the same with my PHPMyAdmin tool but it has been an item in my wish list. I have started working on this and thought of sharing my experiences with the fellow buddies via this blog. 

Let us take it step by step. 

At first, we need to export the database of our choice (if there are many different databases available) and export it as a .sql file via command line. In order to achieve this, we have a command called **mysqldump** (mysqldump.exe in Windows, mysqldump.sh in Linux/Mac). 

**Note**: You should ensure that the directory containing the mysqldump executable is in the PATH environment variable, otherwise the terminal will throw a command not found error.  Otherwise, you can navigate to the directory where the mysqldump executable is present. 

The Syntax takes the form as follows.

```sql
mysqldump -u <UserName> -p [<Password>] <databaseName>
```

```sql
C:\installedSoft\xampp\mysql\bin                                                       
λ mysqldump.exe -u raghs -p itsraghz > itsraghz-export-20Oct2019.sql                   
Enter password: *************  
``` 
The above command has the following parts. 

| Option | Description | Remarks |
| ------------- |:-------------:| -----:|
| **mysqldump.exe**     | the actual executable file to invoke | Ensure you are there in the directory where the executable is present or the directory is available in the PATH environment variable |
| **-u raghs**      | the username to the database|   - |
| **-p** |  indicator for the password, the terminal will ask you further to enter the same     |    It is the best practice NOT to enter the password, so that the password is NOT saved in the .bash_profile (in Linux) |
|** itsraghz ** | name of the database I wanted to export | -- | 
| **&gt;**  | Standard redirection operator to redirect the output of one command to another |  -- |
| **itsraghz-export-20Oct2019.sql** | the output file name where the exported database should be saved. | The file gets saved in same directory where I am in. If needed, you can specify the different folder name prefixed to the output so as to store the file separately. |

The terminal does not show any message if the export is successfully done. You get to hear from it only when there is an error. No error means you are good :)

We need to explicitly list the contents and check for the file what we are expecting. 

```bash
C:\installedSoft\xampp\mysql\bin                                                       
λ ls -ltrh *.sql                                                                       
-rw-r--r-- 1 raghs 197610 7.3M Oct 20 21:05 itsraghz-export-20Oct2019.sql 
```
If you see, the file gets successfully generated and it is of size 7.3 MB. 

There are several different customization we can make to the mysqldump like the formatting, output to be compressed (zip rather than the .sql to save the file size) etc., 

We will see them in subsequent posts, along with the complete automation of the same in a batch file (in Windows) or the shell script in Linux. 