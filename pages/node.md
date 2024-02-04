# Node

## Introduction

Node can be used to do server side scripting.

## Installation

In your jail run `sudo pkg install node` to install node.
Also run `sudo pkg install npm` to be able to install npm packages.

## Running node

As an example, follow the following steps to set up an example project in your jail:

- Change to a directory where you want the project to live.
- Run `fetch https://mvoortman.it.pointpark.edu/cmps-480.tar.gz`
- Extract with `tar xfz cmps-480.tar.gz`
- Change into the extracted directory with `cd cmps-480`
- Start the server with `node cmps-480.js` (ideally using [tmux](tmux) so that it keeps running).
- You should see `Server started on localhost: 3000; press Ctrl-C to terminate....`

## Configuring Nginx

To access the website, you need to forward an nginx path to port 3000:

- Make sure you have [nginx](homepage-setup) installed and running.
- Install and configure [Let's Encrypt](lets-encrypt) next.
- Make sure you do the proxy part at the bottom as well.
- Finally, browse to `https://$USERNAME.it.pointpark.edu/project/` (replace `$USERNAME` with your actual username) to see the end result.
