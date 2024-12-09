# PowerShell User Creation Script



## Objective



The objective of this lab was to automate the creation of user accounts in Active Directory using a PowerShell script. The lab involved setting up and managing a PowerShell environment, configuring necessary execution policies, and defining variables to handle user information from a text file. By scripting the `New-AdUser` command and running it through a `foreach` loop, the lab aimed to efficiently create multiple user accounts in Active Directory, demonstrating skills in automation, scripting, and user management within a virtualized lab setting.

## Skills Learned



- **PowerShell Scripting**:
    - Writing and executing PowerShell scripts.
    - Using variables and loops within scripts.
    - Enabling execution policies for running scripts.
- **Active Directory Management**:
    - Creating user accounts in Active Directory.
    - Using the `New-AdUser` command to automate user creation.
    - Managing user information from external files (e.g., `names.txt`).
- **Automation**:
    - Automating repetitive tasks through scripting.
    - Implementing a `foreach` loop to process multiple inputs.
- **System Administration**:
    - Setting up and configuring a PowerShell environment.
    - Changing directories and managing file paths.
    - Running administrative commands and scripts.
- **File Management**:
    - Creating and managing text files for user data.
- **Troubleshooting and Problem-Solving**:
    - Ensuring scripts run correctly and efficiently.
    - Addressing issues such as script execution policies and correct variable usage.
- **Understanding of Execution Policies**:
    - Setting and understanding execution policies for running PowerShell scripts in a lab environment.

## Tools Used



- **PowerShell**: For scripting and automating the creation of user accounts in Active Directory.
- **Windows PowerShell ISE**: Integrated Scripting Environment used to write, test, and run PowerShell scripts.
- **Active Directory**: For managing users, groups, and organizational units.
- **Windows Server 2019**: The operating system used for the Active Directory environment.

## Steps



![powershell-1.png](PowerShell%20-%20Add%20Users%20with%20Script/powershell-1.png)

1. I begin by creating a text file full of names.

![powershell-2.png](PowerShell%20-%20Add%20Users%20with%20Script/powershell-2.png)

1. Click on windows start menu click —> windows PowerShell and right-click on Windows PowerShell ISE —>More—>Run as Administrator.

![powershell-3.png](PowerShell%20-%20Add%20Users%20with%20Script/powershell-3.png)

1. Next we need to enable the execution of scripts in order to run our PowerShell script. This is not a command we would run on a live deployment. This is strictly because it’s a lab environment. The command is: Set-ExecutionPolicy Unrestricted. After the command is executed we select “yes to all” in order to apply it.

![powershell-5.png](PowerShell%20-%20Add%20Users%20with%20Script/powershell-5.png)

1. Change Directory to the location of where the names.txt file is.

![powershell-4.png](PowerShell%20-%20Add%20Users%20with%20Script/powershell-4.png)

1. The screenshot above displays our PowerShell script. At the top, we create a variable to set a password for each user account created. We also define variables for the first and last names of users, which are pulled from our `names.txt` file. Then, we have a `$password` variable that converts the `$PASSWORD_FOR_USERS` variable into an object that PowerShell can use with the `New-AdUser` command below. For the `foreach` loop, the `$n` variable identifies each line in our `names.txt` file. Lastly, after defining how our variables should function, the `New-AdUser` command is executed with sub-commands to create new user accounts using the respective variable inputs.

![powershell-6.png](PowerShell%20-%20Add%20Users%20with%20Script/powershell-6.png)

1. Click on the play icon and click Run Once.

![powershell-7.png](PowerShell%20-%20Add%20Users%20with%20Script/powershell-7.png)

1. The users are now created. If we go to Start Menu —>Windows Administrative Tools —> Active Directory Users and Computers. Click on [mydomain.com](http://mydomain.com) and open up “_USERS” we now see all of our created users.
