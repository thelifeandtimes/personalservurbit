# Moving a pier

Being able to rapidly move your pier around the world, between local and remote machines, and across different hosts is key to Urbit's value prop. The steps to do this are as follow:

## From VPS to Local Machine, using the local machine

### While ssh'd into your VPS
1. Stop your ship with `ctrl+d`
2. Create a tarball with the command `tar -czvf sampel-palnet.tar.gz /path/to/pier`

## On a terminal for your local machine, from your `/urbit` directory
3. Securely copy files from your VPS using the following command `scp remote_username@10.10.0.2:~/urbit/sampel-palnet.tar.gz ~/urbit`
4. Uncompress the tarball with the command `tar -xzvf sampel-palnet.tar.gz`
5. Reboot your urbit  using `./urbit sampel-palnet` (along with any specific flags for ames/UDP ports or other things)
6. Delete the old, now out of date tarball on your local machine in your `~/urbit` directory, by running `rm -rf sampel-palnet.tar.gz` **!!!MAKE SURE YOU ARE DELETING THE TARBALL, NOT YOUR ACTUAL PIER!!!**

## While ssh'd into your VPS
7. Delete your old, now out of date pier by running `rm -rf sampel-palnet` in your urbit directory.
8. Delete your old, now out of date tarball by running `rm -rf sampel-palnet.tar.gz` in your urbit directory.

## From Local Machine to VPS

### While in a terminal on your local machine
1. Stop your ship with `ctrl+d`
2. Create a tarball with the command `tar -czvf sampel-palnet.tar.gz /path/to/pier`
3. Push the compressed pier into your virtual server by running `scp sampel-palnet.tar.gz remote_username@10.10.0.2:~/urbit/`

## While ssh'd into your VPS
11. Uncompress the tarball with the command `tar -xzvf sampel-palnet.tar.gz`
12. Reboot your urbit with `./urbit sampel-palnet` (along with any specific flags for ames/UDP ports or other things)
13. Delete the now out of date tarball by running `rm -rf sampel-palnet.tar.gz` **!!!MAKE SURE YOU ARE DELETING THE TARBALL, NOT YOUR ACTUAL PIER!!!**

## After confirming your ship to be booted and operating correctly, on your local machine 
14. Delete the extra copy of your now out of date, pier by running `rm -rf sampel-palnet` in your urbit directory.
15. Delete the extra copy of your now out of date, tarball by running `rm -rf sampel-palnet.tar.gz` in your urbit directory.

## General notes
The scp command syntax take the following form:
`scp [OPTION] [user@]SRC_HOST:]file1 [user@]DEST_HOST:]file2`
