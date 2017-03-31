# simplehtmlsecured
Quickly password-protect a file [with encryption] that's being hosted on your github.io

This repo simply explains how to use the Secure HTML 1.6 program in Windows 10 to quickly encrypt an html file and, also shows you how to place that file in your username.github.io repo for public access using the password you choose.

![Alt](http://www.buildwebsite4u.com/tools/img/sh.gif "sh exe program")

Download sh.exe at [link](http://www.buildwebsite4u.com/tools/secure-html.shtml "sh exe download"), or here [link](http://www.buildwebsite4u.com/cgi-bin/t.cgi?sh.exe "Title").

**AGAIN..** this is a guide that shows you how to use the sh.exe program within Windows 10: sh.exe was fully created by BuildWebSite4u.com Copyright © 2002-2017

# Steps in macOS using Virtual Box -- SKIP to #5 if you're running a stable Windows 10 already silly!

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

# #1 
Currently you can see this in action at the following link: https://st-fresh.github.io/interference/mobile/interference3.html
However, you can't access this unless I give you a password, so if you want to see the demo then ping me on twitter @mrdignitty (you need a working github account and reason to view). 

# #2 
## Reviewing the demo
I started with an interfernce.html file, file was saved using the IntelliJ editor,
Once saved I used the [ Input ] feature of the sh.exe GUI to browse my directory for the `interference.html` file,
Once you select it the field next to [ Input ] in sh.exe GUI should populate with the directory-pathway to the file,
Also, at the same time,
The field next to [ Output ] in the sh.exe GUI will populate with "_interference.html" the directory-pathway for your new file,
I suggest NOT using this file that starts with "_" because I had weird behavior when my github.io page tried to access and decrypt it,
Instead I chose this name "interference3.html" and clicked [ Encode ] button at base of sh.exe GUI,
This will cause the new Output file that you named to show up in the exact same directory,
### IF you choose the SAME exact file-name:
You will be warned that you are about to overwrite the existing files data before saving to the directory with an alert in the sh.exe GUI -- make your choice in dialogue. 

# #3
# Using you newly encrypted file
Navigate to your git repo with cd < repo name > in your CLI,
Make sure the newly encrypted file is within a git repo -- you can copy and paste it from one directory to another just fine,
Run ` git status ` in CLI to make sure git sees the new addition to your repo,
Run ` git add -yourPreference ` in CLI to add it to the next commit, 
Run ` git push origin -yourOrigin ` in CLI to make the file live in your github.io repo to be served at HTTPS,

# #4
## Testing access
Return to your browser and go to ` https://handle.github.io/path-to-encrypted-html-file-you-uploaded `,
You should get an alert immediately.. However, on some browsers your alerts are a security risk ! uhoh,

Refer to #4.I if you need to get this working in the Brave browser, OR,
You can rewrite how your encrypted file displays the password field by editing the contents of the Shadow Root of the DOCUMENT BODY,
To do this you must use your for example Chrome DevTools Inspector,
Once your Inspector is open click on ` #shadow-root open ` to access the root for ` <body> reveal `,
Click ` reveal `,
You will see the JS that controls the all based on ` documet.write() ` method,
Now you have the current root that's loading, 
Right-Click on ` <script language="JavaScript"> ` DOM element within your inspectors [ Elements ] tab,
Choose [ Edit as HTML ],
This should place a new cursor within the JS that starts with ` <!--var _$a=###,_$b=new Array( `,
Select-all of this text, and Copy it to OS memory,
Paste into new File within your editor of choice, mind is IntelliJ,
You can now proceed to first compare this to the JS shadow root that you have locally before moving forward, should be exact same,
Proceed then within this newly created file to make your changes to the Alert window behavior, or remove it altogether,
At this time Brave.com Browser does block your .html file


# #5
< explain ISO obtain >
< explain Virtual Box dl >
< explain new Win10VM >
< give troubleshooting resources >


