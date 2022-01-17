# Jump Box

Starting January 2022, it is not possible anymore to directly connect to your jail over SSH. Most other ports (e.g., MySQL) are also closed but ports 80 (HTTP) and 443 (HTTPS) are still open. Due to externally imposed restrictions, you now need to connect to a so called [jump box](https://en.wikipedia.org/wiki/Jump_server) before you can connect to your jail. Please follow these steps to achieve this:

- If you do not have a jail yet, please [contact](contact) your instructor first.
- Connect to https://ts-cmps.pointpark.edu using a browser.
- Log in with your Point Park credentials (do *not* use your jail credentials).
- Once logged in you can use PuTTY, FileZilla, the MySQL Workbench, etc. to connect to your jail in the normal way (make sure to use your jail credentials).
- After the previous steps you can follow any other [tutorial](tutorials) on this site and it should work.
- [Contact](contact) your instructor if you run into problems.
