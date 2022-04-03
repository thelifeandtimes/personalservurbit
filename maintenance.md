# Melding a pier

`meld` is a tool from `urbit-worker` that deduplicates persistent state. It is run by using the following command: `./urbit-worker meld <pier>` 
Unfortunately it takes a decent amount of memory to properly run so depending on the resources on your VPS, you may need to pull it down to a local machine, run meld locally, and then push your pier back up to the cloud server. The steps to do this are as follow:

## While ssh'd into your VPS
1. Stop your ship with `ctrl+d`
2. Create a tarball with the command `tar -czvf sampel-palnet.tar.gz /path/to/pier`

## On a terminal for your local machine, from your `/urbit` directory
3. Securely copy files from your VPS using the following command `scp remote_username@10.10.0.2:~/urbit/sampel-palnet.tar.gz ~/urbit`
4. Uncompress the tarball with the command `tar -xzvf sampel-palnet.tar.gz`
5. Run your urbit worker process using `./urbit-worker meld sampel-palnet`
6. Delete the old, unmelded tarball by running `rm -rf sampel-palnet.tar.gz`
7. Recreate a tarball of your newly melded peir with the command `tar -czvf sampel-palnet.tar.gz /path/to/pier`

## While ssh'd into your VPS
8. Delete your old, unmelded pier by running `rm -rf sampel-palnet` in your urbit directory.
9. Delete your old, unmelded tarball by running `rm -rf sampel-palnet.tar.gz` in your urbit directory.

## Back in the terminal on your local machine
10. Push the compressed pier back into your virtual server by running `scp sampel-palnet.tar.gz remote_username@10.10.0.2:~/urbit/`

## While ssh'd into your VPS
11. Uncompress the tarball with the command `tar -xzvf sampel-palnet.tar.gz`
12. Reboot your urbit with `./urbit sampel-palnet` (along with any specific flags for ames/UDP ports or other things)
13. Delete the now out of date tarball by running `rm -rf sampel-palnet.tar.gz` **!!!MAKE SURE YOU ARE DELETING THE TARBALL, NOT YOUR ACTUAL PIER!!!**

## After confirming your ship to be booted and operating correctly, on your local machine 
14. Delete the extra copy of your melded, but now out of date, pier by running `rm -rf sampel-palnet` in your urbit directory.
15. Delete the extra copy of your melded, but now out of date, tarball by running `rm -rf sampel-palnet.tar.gz` in your urbit directory.

## General notes
The scp command syntax take the following form:
`scp [OPTION] [user@]SRC_HOST:]file1 [user@]DEST_HOST:]file2`
