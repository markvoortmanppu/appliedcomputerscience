# VirtualBox

## Introduction

[VirtualBox](https://en.wikipedia.org/wiki/VirtualBox) can be used to run virtual machines and is used in the [CMPS 261 Server Management](cmps-261) course.

## Installation

Follow these steps to install VirtualBox:

- Go to [virtualbox.org](https://www.virtualbox.org/) and download the latest version.
- NOTE: If you are on an Apple computer with an M1 CPU or later you currently need to download the ARM64 development snapshot [here](https://www.virtualbox.org/wiki/Testbuilds).
- Once VirtualBox is downloaded, run the installer and keep the default options or modify them based on your preferences.

## FreeBSD VM creation

Follow these steps to create a FreeBSD virtual machine:

- Go to the [FreeBSD](https://www.freebsd.org/) website and download a recent amd64 disc1 ISO release file.
- In VirtualBox, click on the New button to start the creation of a new virtual machine instance.
- On the first screen, use `freebsd` (or similar) for the name and select the downloaded ISO file.
- Run through the rest of the installer and keep the default options or modify them based on your preferences.
- Once done, start the VM and the FreeBSD installer will run.
- In most cases, you should pick the default option by pressing enter (see below for exceptions).
- For hostname, you can just enter `freebsd`.
- On the screen where you see `VBOX HARDDISK`, make sure to press space first (to select) and only then press enter.
- On the next screen make sure that you select `Yes`.
- You can pick (and remember) a root password or keep it blank for the time being.
- Select `No` when it is asking to configure IPv6.
- For the question on whether the machine's CMOS clock set to UTC, select `No` and make sure to select the correct region, country, and time zone.
- Select `No` when it is asking to add a new user to the system.
- Make sure to remove the CD before rebooting (or it will boot from the installation CD again).
- More information can be found in the [FreeBSD Handbook](https://docs.freebsd.org/en/books/handbook/bsdinstall/).

## Configuring port forwarding

To be able to connect to your VM over SSH, follow these steps:

- Go to settings for your FreeBSD virtual machine.
- Click on the Expert option and go to network.
- Open the Port Forwarding screen.
- Add a new entry with SSH as Name, 2222 as host port, and 22 as Guest Port (keep other fields blank).
- Connect to localhost port 2222 over SSH with the terminal or FileZilla to make sure that you can connect.
- Also, with FreeBSD you can only ssh to non-root user accounts so you have to add a user (use the `adduser` program).
- For example, you should be able to use this command: `ssh -p 2222 user@localhost` where you replace user with your username.
