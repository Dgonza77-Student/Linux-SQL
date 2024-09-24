# Bash Scripting: Configuring File Permissions in Linux

## Objective

In this lab activity, you’ll explore Linux commands to manage file and directory permissions. The goal is to control and configure access to specific files and directories, ensuring proper **authorization** by restricting who can read, write, or execute certain files. This process is essential for maintaining the security of a system and protecting sensitive information from unauthorized access.

### Skills Learned
- Understanding Linux file permissions (read, write, execute) for users, groups, and others.
- Utilizing `chmod` to modify file permissions effectively.
- Analyzing and modifying hidden file permissions.
- Strengthening security by controlling access to directories.

### Tools Used
- Linux OS (command-line interface)
- `chmod` (change mode) command for file permissions
- `ls` command for listing directory contents and permissions
- `cd` command for changing directories

## Steps

### Step 1: Navigating to the `projects` Directory

First I opened the console and navigated to the projects directory under the researcher 2 user by using the LS command to list the directories and the cd command to change to the project directory

![image](https://github.com/user-attachments/assets/535f55a8-5940-4fdb-876d-4416cbb4fbd4)

### Step 2: Listing File Permissions

To list the permissions of the files in the projects directory I utilized the following command
``ls -l``

![image](https://github.com/user-attachments/assets/55d5bbeb-4983-406e-81aa-65a72e0e2aaa)

Following the command, many 10-character strings are listed such as "drwx--x---" which indicate the permissions set on the file. 

### File Information Fields
Each entry has several columns:

| Field            | Explanation                                                                 |
|------------------|-----------------------------------------------------------------------------|
| `drwx--x---`     | Permissions for the directory or file (explained below).                     |
| `2`              | Number of links (in this case, subdirectories or references).                |
| `researcher2`    | Owner: The user who owns the directory or file.                              |
| `research_team`  | Group: The group that owns the directory or file.                            |
| `4096`           | Size of the file or directory in bytes.                                      |
| `Sep 23 22:04`   | Last modification date and time.                                             |
| `.` and `..`     | File or directory name (in this case, the current and parent directories).   |


| Character Position  | Description                                                |
|---------------------|------------------------------------------------------------|
| **1st Character**    | `d` for directory, `-` for file                            |
| **2nd-4th Characters** | Permissions for the **user** (read `r`, write `w`, execute `x`) |
| **5th-7th Characters** | Permissions for the **group** (read `r`, write `w`, execute `x`) |
| **8th-10th Characters** | Permissions for **others** (read `r`, write `w`, execute `x`)  |




## Step 3: Viewing Hidden Files

To include hidden files in the list of file permissions, I used the ``ls -la`` command:

![image](https://github.com/user-attachments/assets/99640433-fa4f-4fd9-8715-8b0282081ab9)bash

After executing the command, .project_x.txt is shown.



## Step 4: Changing Permissions for project_k.txt

With the information gathered, I begin to determine which of the files have incorrect permissions and make changes as needed. This is done in order to remove any users with unathorized access to the system and strengthen the security on the system overall. This plays into the principle of least privilege 

One of the tasks assigned is that "Others" owner group should not have write permissions for any files in the projects directory.

![image](https://github.com/user-attachments/assets/02d45329-d94d-48fc-b01d-ac7aacbfa0db)

We can see here that the .project_k.txt file has both read and write permissions for the "Others" owner group

In order to remove the write permission from the "Others" Owner group I execute the command chmod o-w project_k.txt

| Command Part         | Explanation                                         |
|----------------------|-----------------------------------------------------|
| `chmod`              | Change file or directory permissions                |
| `o`                  | Refers to "others" (users who are not the owner or group) |
| `-w`                 | Remove write permission                             |
| `project_k.txt`      | The file to which the command is being applied      |

After running the command and checking the directory, we can see that the write command has been removed from the "Others" Owner group for the file


![image](https://github.com/user-attachments/assets/992984c4-388e-4ba5-adba-186d977efe8a)





## Step 5: Adjusting Permissions for project_m.txt



My next set of instructions is to make sure that the project_m.txt file is not readable or writeable by the group or "other" permission group. The only group that should have those permissions is the user permission group.

To complete the task I first list out the files in the projects directory and see what permissions are already set to the project_m.txt file

![image](https://github.com/user-attachments/assets/ee93c76d-c501-459f-857c-6fd583bb4847)

In the above image I have highlighted the "group" permissions in blue and the "Other" permissions group in pink.

As listed, the "Other" permission group has no permissions while the "group" permission group  only has the read permission.

Furthermore, we can see that the user group already has read and write permissions (Highlighed in yellow)

![image](https://github.com/user-attachments/assets/fceb3de5-1e09-4e10-ac52-617de1a25a50)

In order to meet project requirements, I remove the read permission from "group" permissions via ``chmod g-r project_m.txt``


| Command Part         | Explanation                                         |
|----------------------|-----------------------------------------------------|
| `chmod`              | Change file or directory permissions                |
| `g`                  | Refers to the "group" (the group owner of the file) |
| `-r`                 | Remove read permission                              |
| `project_m.txt`      | The file to which the command is being applied      |


Current Status of permissions:

![image](https://github.com/user-attachments/assets/9850598d-b065-4f76-913d-5260b3be8043)







## Step 6: Modifying Hidden File Permissions for .project_x.txt
Upon inspection, I found that the hidden file .project_x.txt had write permissions for both the user and group, which was inappropriate for this file.

(User highlighted in red and group highlighted in blue)

![image](https://github.com/user-attachments/assets/187e95a4-4768-4b0c-a53d-26676b87d865)


To remove the write permission for both the user and group but still allow them to read, I used:


``chmod ug=r .project_x.txt``

This command ensures that only read permissions are left for both the user and group while removing any other permissions.

| Command Part         | Explanation                                                   |
|----------------------|---------------------------------------------------------------|
| `chmod`              | Change file or directory permissions                          |
| `ug`                 | Refers to both "user" (u) and "group" (g)                     |
| `=r`                 | Set the permission to "read" (removes all other permissions)  |
| `.project_x.txt`     | The file to which the command is being applied                |


![image](https://github.com/user-attachments/assets/9747aaca-76a6-468f-8faa-d303151dbe64)

(User is highlighted in red and group is highlighted in blue)

## Step 7: Changing Directory Permissions for drafts
Lastly, I navigated to the drafts directory to modify its permissions.

``cd Drafts``

We can see the drafts directory being represented by "." and our previous directory (Projects) being represented by ".." alongside their respective permissions

![image](https://github.com/user-attachments/assets/e02d2c76-584a-41e9-9fd8-21175866c7bc)

When looking at the permissions we can also see that the user groups for the "Drafts" directory has permission to access the drafts directory and its contents

Our objective is then to remove the execute permission for the group from the drafts directory and we do that by running the command chmod g-x.

After the execution of the command, we can see the execute permission removed from the group owner group.

![image](https://github.com/user-attachments/assets/785fd851-6204-48bc-b328-8b149ac1809b)


### Conclusion
In this lab, I used various Linux commands to manage file and directory permissions. By modifying permissions with the chmod command, I ensured that unauthorized users and groups do not have access to sensitive files or directories. This lab demonstrates the importance of configuring file permissions to maintain system security and prevent unauthorized access to critical resources.










---




