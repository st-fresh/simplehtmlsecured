# simplehtmlsecured
Quickly password-protect a file [with encryption] that's being hosted on your github.io

This repo simply explains how to use the Secure HTML 1.6 program in Windows 10 to quickly encrypt an html file and, also shows you how to place that file in your username.github.io repo for public access using the password you choose.

![Alt](http://www.buildwebsite4u.com/tools/img/sh.gif "sh exe program")

# #Prelim 
Download sh.exe at [link](http://www.buildwebsite4u.com/tools/secure-html.shtml "sh exe download"), or here [link](http://www.buildwebsite4u.com/cgi-bin/t.cgi?sh.exe "Title").

**AGAIN..** this is a guide that shows you how to use the sh.exe program within Windows 10: sh.exe was fully created by BuildWebSite4u.com Copyright © 2002-2017

# For Steps in macOS using Virtual Box SKIP to #5 then refer back to #1 once you have successfully ran sh.exe in Win10 OS -- SKIP to #1 if you're running a stable Windows 10 already silly!

Here's how to create a password protected HTML page quickly...
1) Press the button Input File and select the desired HTML file.
2) Correct the path and name of Output File, if needed. If you want to overwrite the input file, you can use the same name.
3) Enter Password (not less than 4 characters).
4) Check the box View Output File if you want to view the password protected HTML file in your default browser.
5) Press the Encode button.
Note: If the input file is already encrypted, the program detects it, names the final button Decode and restores the original file (of course, if you enter the correct password).

## Other features
### High ASCII codes
Secure HTML correctly encodes and decodes files containing high ASCII codes (128...255). So the program can protect non-English HTML pages in which high ASCII codes represent national characters.

### Command line parameters
The program accepts command line parameters, so that you can automate your work...
`sh [-iInFile] [-oOutFile] [-pPsw] [-v] [-c]`
where...
* -iInFile - Input File.
* -oOutFile - Output File.
* -pPsw - Password.
* -v - View Output File.
* -s - Silent (no errors or warnings).
* -c - Encode and Exit.
If a filename contains spaces, enclose the entire filename in quotation marks. For example,
`sh -i"c:\Program Files\in.htm" -o"c:\Program Files\out.htm" -p12345 -c`

# #1 in Demo/Correct Functionality ( End-Results you should get yourself! mmhmm )
Currently you can see this in action at the following link: https://st-fresh.github.io/interference/mobile/interference3.html
However, you can't access this unless I give you a password, so if you want to see the demo then ping me on twitter @mrdignitty (you need a working github account and reason to view). 

# #2 Demo in Laymens terms/Directions after sh.exe opens successfully
## Reviewing the demo
#### 2.I/ I started with an interfernce.html file, file was saved using IntelliJ [github.com/JetBrains/intellij-community]  editor
#### 2.II/ Once saved I used the [ Input ] feature of the sh.exe GUI to browse my directory for the `interference.html` file
#### 2.III/ Once you select it the field next to [ Input ] in sh.exe GUI should populate with the directory-pathway to the file
Also, at the same time
#### 2.IV/ The field next to [ Output ] in the sh.exe GUI will populate with "_interference.html" the directory-pathway for your new file
#### 2.V/ I suggest NOT using this file that starts with "_" because I had weird behavior when my github.io page tried to access and decrypt it
#### 2.VI/ Instead I chose this name "interference3.html" and clicked [ Encode ] button at base of sh.exe GUI
This will cause the new Output file that you named to show up in the exact same directory
#### 2.VII/ IF you choose the SAME exact file-name:
You will be warned that you are about to overwrite the existing files data before saving to the directory with an alert in the sh.exe GUI -- make your choice in dialogue. 

# #3  Encrypting using sh.exe and adding the encrypted file to yor github.io pages repo
# Using your newly encrypted file
#### 3.I/ Navigate to your git repo with cd < repo name > in your CLI,
#### 3.II/ Make sure the newly encrypted file is within a git repo -- you can copy and paste it from one directory to another just fine,
#### 3.III/ Run ` git status ` in CLI to make sure git sees the new addition to your repo,
#### 3.IV/ Run ` git add -yourPreference ` in CLI to add it to the next commit, 
#### 3.V/ Run ` git push origin -yourOrigin ` in CLI to make the file live in your github.io repo to be served at HTTPS,

# #4 Testing your file-encrypted file-access
## Testing access
#### 4.I/ Return to your browser and go to ` https://handle.github.io/path-to-encrypted-html-file-you-uploaded `,
#### 4.II/ You should get an alert immediately [ enter your password ].. However, on some browsers your alerts are a security risk ! uhoh, refer to #5.XI to find solutions if you're running for example the Brave.com Browser.

# #5 Custom Options 
### For VirtualBox in MacOS you need to, 
Download Virtual Box from: https://www.virtualbox.org/,
Next you need to obtain a Win10 ISO file, 
#### 5.I/ If you can't do this on your own then just ping me on gitter (st-fresh) or twitter (mrdignitty) and I will get a working ISO file to you,
#### 5.II/ In the VirtualBox apps menu on your system use ⌘N to Create a New OS > Choose Your-Name > Choose Type: Microsoft Windows > Choose: Windows 10 64/32-bit depending on your PC > Choose Default Memory Size > Choose Virtual HD > You will be prompted for your ISO file > Browse for your ISO file and attach it to your new OS VM > File will proceed to load when you lauch your new Win10 VM > Now install Win10 > Once you've successfully installed Win10 OS and are within it.. navigate to link in this gudie above under [ Prelim ] using Microsoft Edge Browser > Download sh.exe program > Open sh.exe and then proceed to #2 above to finish creating your encrypted .html files

### For controlling how your passcode dialogue box fires:
#### 5.III/ You can rewrite how your encrypted file displays the password field by editing the contents of the Shadow Root of the DOCUMENT BODY,
To do this you must use your for example Chrome DevTools Inspector and an IDE(or Code Editor Program like Sublime/Atom/etc),
#### 5.IV/ Once your Inspector is open click on ` #shadow-root open ` to access the root called ` <body> reveal `,
#### 5.V/ Click ` reveal `,
You will see the JS that controls the dialogue is based on ` documet.write() ` method,
Now you have the current root that's loading, 
#### 5.VI/ Right-Click on ` <script language="JavaScript"> ` DOM element within your inspectors [ Elements ] tab,
#### 5.VII/ Choose [ Edit as HTML ],
This should place a new cursor within the JS that starts with ` <!--var _$a=###,_$b=new Array( `,
#### 5.VIII/ Select-all of this text, and Copy it to OS memory,
#### 5.IX/ Paste into new File within your editor(or IDE) of choice, my editor is IntelliJ (github.com/JetBrains/intellij-community),
#### 5.X/ Proceed then within this newly created file to make your changes to the Alert window behavior, or remove it altogether and replace with your own passcode dialogue logic:
Notice that this JS corresponds directly with the script block that is withing your actual encrypted .html file itself, You should then past this script into your encrypted .html file where you see the following ` <BODY><script language="JavaScript">
<!--
var _$a=###,_$b=new Array( `, After updating this file your new Dialogue/Alert Window functionality should be represented on within the served front-end experience at https://handle.github.io/path-to-your-encrypted-html-file
#### 5.XI/ At this time Brave.com Browser does block your .html file [ Issue - Solve using specific Brave Preferences???? ] -- refer to #6 to handle these issues


# #6 Handling Issues
For now just ping me on twitter @mrdignitty or gitter @st-fresh/st.fresh
< give troubleshooting resources for Brave etc. >


