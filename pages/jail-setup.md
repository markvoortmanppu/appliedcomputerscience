# Jail Setup

## Obtaining an Jail

Your environment is usually created when you take a class that requires work on the server. This is a type of remote connection but normally only uses a command line text interface. Ask the instructor to set up an account for you. Your environment is identified with your Point Park username.

## Connecting to Your Jail

Tip: Connecting to your environment is very similar to setting up a remote desktop connection, but then without the graphical user interface.
Because your environment runs remotely you need software to connect (through the SSH protocol). On Windows one of the best programs is PuTTY. On Mac OS X one could use the ssh program from the Terminal (go to the Launchpad and type Terminal). When running PuTTY you have to set the server you are connecting to, so simply enter as Host Name

```username@username.it.pointpark.edu```

where you replace username with your actual account name. When using ssh from the terminal you simply type

```ssh username@username.it.pointpark.edu```

In both cases you will be prompted for your password. Your initial password is the same as your username initially, but you will be forced to change it immediately.
Note: You should pick a password that is hard to guess and you do not use anywhere else!

Below are screen shots of both PuTTY (left) and a terminal window (right) with the required information filled out (click on them for a larger version). Note that you have to replace all occurrences of mvoortman with your username.

![PuTTy](images/jail-putty.png)

![Terminal](images/jail-terminal.png)

## Changing the Timezone

When you enter

```date```

it will display the time for the wrong timezone (unless this has already been fixed). To address this issue first change to the root user

```su```

then enter the timezone setup utility

```tzsetup```

Select `No` for the first dialog, then America, and scroll down almost all the way to the bottom for the United States. Next select Eastern Time (or whatever is appropriate) and confirm by selecting `Yes`. After running date again it should show the correct timezone.
Finally, exit the root account

```exit```

## Video

The steps above are also captured in the following video:
[Jail Setup Video](videos/jail-setup.mp4)
