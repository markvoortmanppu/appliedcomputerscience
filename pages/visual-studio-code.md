# Visual Studio Code

## Introduction

Visual Studio Code, also known as VS Code, is a very popular code editor that we recommend. You can download it [here](https://code.visualstudio.com/).

## Local Code Editing

Local code editing works like any regular program, just run VS Code and open a file, edit, and then save. There are also many plugins available if you are looking for additional functionality. After you are done editing you may need to use [FileZilla](filezilla) to upload the files to your [jail](jail-setup).

## Remote Code Editing

In most courses you will need to host your websites or applications in your [jail](jail-setup). Therefore, it would be very convenient to be able to edit the code in your jail remotely from your local computer. The following steps achive this:

* Open Visual Studio Code.
* In the menu on the left click on the Extensions tab.
* Search for `ssh fs`.
* Install SSH FS (the author should be Kelvin Schoofs).
* In the menu on the left a new icon will show up (looking like a terminal), please click on it.
* Create on the icon to create a new configuration.
* Give the configuration a name.
* Enter `$USERNAME.it.pointpark.edu` under Host (make sure to replace `$USERNAME` with your actual username).
* Under Root enter `/home/$USERNAME`.
* Under Username enter your username.
* Under Password enter your password (it is much better to set up keys if you know how to).
* Save the configuration.
* The configuration will be listed, now click on the "Add as Workspace folder" icon.
* You can now browse the files in your jail, and edit them directly!

## Git and GitHub

In addition to editing the files, in most cases you also have to commit the changes to [git](git) and push them to [GitHub](github). You can do this by connecting to your jail using [the terminal or PuTTY](jail-setup) and running the appropriate commands.
