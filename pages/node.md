# Node

## Introduction

Node can be used to do server side scripting.

## Installation

In your jail run `pkg install node`.

## Running node

As an example, follow the following steps to set up an example project in your jail:

- Change to a directory where you want the project to live.
- Run `fetch https://mvoortman.it.pointpark.edu/cmps-480.js`
- Extract with `tar xfz cmps-480.tar.gz`
- Change into the extracted directory with `cd cmps-480`
- Start the server with `node cmps-480.js` (ideally using [tmux](tmux) so that it keeps running).
