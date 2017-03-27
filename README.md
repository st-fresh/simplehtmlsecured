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
