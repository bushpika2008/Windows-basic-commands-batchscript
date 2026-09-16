# Windows-basic-commands-batchscript
Ex08-Windows-basic-commands-batchscript

# AIM:
To execute Windows basic commands and batch scripting

# DESIGN STEPS:

### Step 1:

Navigate to any Windows environment installed on the system or installed inside a virtual environment like virtual box/vmware 

### Step 2:

Write the Windows commands / batch file . Save each script in a file with a .bat extension. Ensure you have the necessary permissions to perform the operations. Adapt paths as needed based on your system configuration.
### Step 3:

Execute the necessary commands/batch file for the desired output. 




# WINDOWS COMMANDS:
## Exercise 1: Basic Directory and File Operations
Create a directory named "my-folder"
mkdir my-folder

<img width="715" height="182" alt="WhatsApp Image 2026-09-16 at 15 53 21" src="https://github.com/user-attachments/assets/cb25cd91-a8d1-4e8f-ab7a-26223f3147c4" />


## COMMAND AND OUTPUT

Remove the directory "my-folder"
rmdir my-folder

<img width="715" height="182" alt="WhatsApp Image 2026-09-16 at 15 53 21" src="https://github.com/user-attachments/assets/3bf7d8f1-96dc-4c3e-9345-701ded6e03ac" />


## COMMAND AND OUTPUT


Create the file Rose.txt
COPY CON Rose.txt
A clock in a office can never get stolen
Too many employees watch it all the time
<img width="685" height="467" alt="WhatsApp Image 2026-09-16 at 15 56 36" src="https://github.com/user-attachments/assets/198c920b-a439-48b9-868d-78b7896d191c" />


## COMMAND AND OUTPUT


Create the file hello.txt using echo and redirection
echo “hello world” > hello.txt
type hello.txt
<img width="641" height="135" alt="WhatsApp Image 2026-09-16 at 15 57 34" src="https://github.com/user-attachments/assets/6a6436c9-aa43-4206-9f9d-8d29a99bc526" />

## COMMAND AND OUTPUT

Copy the file hello.txt into the file hello1.txt
copy hello.txt hello1.txt
<img width="632" height="232" alt="WhatsApp Image 2026-09-16 at 15 58 20" src="https://github.com/user-attachments/assets/8377efe6-2d3c-4bbb-be74-a1a9c886bd2c" />

## COMMAND AND OUTPUT

Remove the file hello1.txt
del hello1.txt
dir hello1.txt
<img width="737" height="172" alt="WhatsApp Image 2026-09-16 at 15 59 14" src="https://github.com/user-attachments/assets/f29ccade-870d-4ff4-8d58-5550b8225657" />

## COMMAND AND OUTPUT

List out the file hello1.txt in the current directory
assoc | more

<img width="692" height="857" alt="WhatsApp Image 2026-09-16 at 15 59 50" src="https://github.com/user-attachments/assets/a23ffef7-56ac-4c9b-b442-4365dc7d8915" />

## COMMAND AND OUTPUT

List out all the associated file extensions 
fc hello.txt Rose.txt
<img width="632" height="210" alt="WhatsApp Image 2026-09-16 at 16 00 39" src="https://github.com/user-attachments/assets/13134d64-5ef1-4a51-8538-e72fa7d428cd" />

## Exercise 2: Advanced Batch Scripting
Create a batch file named on the desktop. The batch file need to have a variable assigned with a desired name for ex. name="John" and display as "Hello, John".

@echo off
set name=John
echo Hello, %name%!
pause





## OUTPUT

<img width="500" height="137" alt="WhatsApp Image 2026-09-16 at 16 03 13" src="https://github.com/user-attachments/assets/c003f405-03fb-49cd-9bad-f3d0c7da3d23" />


Create a batch file  on the desktop that checks whether a user-input number is odd or not. The script should:
Prompt the user to enter a number.
Calculate the remainder when the number is divided by 2.
Display whether the number is odd or not.
Ask the user if they want to check another number.
Repeat the process if the user enters Y, and exit with a thank-you message if the user enters N.
Handle invalid inputs for the continuation prompt (Y/N) gracefully.


@echo off
:main
set /p number=Enter a number: 
rem Calculate remainder when divided by 2
set /a remainder=%number% %% 2
if %remainder%==1 (
    echo %number% is an odd number.
) else (
    echo %number% is not an odd number.
)
:choice
set /p continue=Do you want to check another number? (Y/N): 
if /i "%continue%"=="Y" goto main
if /i "%continue%"=="N" goto end
echo Invalid choice, please enter Y or N.
goto choice
:end
echo Thank you for using the odd number checker!
pause

## OUTPUT
<img width="610" height="282" alt="WhatsApp Image 2026-09-16 at 16 05 20" src="https://github.com/user-attachments/assets/51a45f0f-0d50-448a-bd95-0972539f3050" />




Write a batch file that uses a FOR loop to iterate over a sequence of numbers (1 to 5) and displays each number with the label Number:. The output should pause at the end.

@echo off
for %%i in (1 2 3 4 5) do (
    echo Number: %%i
)
pause



## OUTPUT
<img width="535" height="240" alt="WhatsApp Image 2026-09-16 at 16 06 37" src="https://github.com/user-attachments/assets/9c388d53-31a7-454e-90ea-911f56d9e8af" />




Write a batch script to check whether a file named sample.txt exists in the current directory. If the file exists, display the message sample.txt exists. Otherwise, display sample.txt does not exist. Pause the script at the end to view the result.

Instructions:
Use the IF EXIST conditional statement.
Make sure the script works for files located in the same directory as the batch file.
Use pause to keep the command window open after displaying the message.
Expected Output (if the file exists):

@echo off
if exist sample.txt (
    echo sample.txt exists.
) else (
    echo sample.txt does not exist.
)
pause



## OUTPUT
<img width="537" height="147" alt="WhatsApp Image 2026-09-16 at 16 07 55" src="https://github.com/user-attachments/assets/b29dcd7c-d323-435b-9611-fe7931aa9bf7" />


Write a batch script that displays a simple menu with three options:
Say Hello – Displays the message Hello, World!
Create a File – Creates a file named newfile.txt with the content This is a new file
Exit – Exits the script with a goodbye message
The script should repeatedly display the menu until the user chooses to exit. Use goto statements to handle menu navigation.

@echo off
:menu
echo 1. Say Hello
echo 2. Create a File
echo 3. Exit
set /p choice=Choose an option: 
if "%choice%"=="1" goto hello
if "%choice%"=="2" goto createfile
if "%choice%"=="3" goto end

:hello
echo Hello, World!
goto menu

:createfile
echo Creating a file...
echo This is a new file > newfile.txt
goto menu
:end
echo Goodbye!
pause



## OUTPUT



<img width="502" height="435" alt="WhatsApp Image 2026-09-16 at 16 09 35" src="https://github.com/user-attachments/assets/719e24a7-a300-4978-b837-b4b5f1100c81" />


# RESULT:
The commands/batch files are executed successfully.

