# FileZilla

## Introduction

FileZilla is a free software, cross-platform FTP application, consisting of FileZilla Client and FileZilla Server. Client binaries are available for Windows, Linux, and Mac OS X, server binaries are available for Windows only. The client supports FTP, SFTP and FTPS (FTP over SSL/TLS). (Source: Wikipedia)

## Installation.

Select "Download FileZilla Client" on [this page](https://filezilla-project.org/) (**do NOT download the server**).

## Configuration

Locate and install the file you downloaded in the previous step.

* Run Filezilla.
* Navigate to File >> Site Manager.
* Select New Site and name it anything you wish.
* In the host field enter `$USERNAME.it.pointpark.edu` or the IP address to your jail. Replace `$USERNAME` with your actual username.
* Change the Protocol to SFTP – SSH File Transfer Protocol.
* Change the Logon Type to Ask for password.
* Enter the username to your name in the Username field.
* No other fields or options need to be changed.
* Press Connect to access your jail.
* Enter the password to your jail when requested.

In the future you can connect straight to your jail by visiting the Site Manager and simply choosing your saved connection (**do NOT use quickconnect**). This can be done via the File menu or the icon on the far left of the FileZilla taskbar.

## Video

[FileZilla Intro Video](videos/filezilla-intro.mp4).
