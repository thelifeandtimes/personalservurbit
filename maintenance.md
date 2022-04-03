# Melding a pier

`meld` is a tool from `urbit-worker` that deduplicates persistent state. It is run by using the following command: `./urbit-worker meld <pier>` 
Unfortunately it takes a decent amount of memory to properly run so depending on the resources on your VPS, you may need to pull it down to a local machine, run meld locally, and then push your pier back up to the cloud server. The steps to do this are as follow:

## While ssh'd into your VPS
1. Stop your ship with `ctrl+d`
2. Create a tarball with the command `tar -czvf sampel-palnet.tar.gz /path/to/pier`
3. Delete your old pier so as to not accidentally mix up which pier is which by running `rm -rf sampel-palnet`

## On a terminal for your local machine, from your `/urbit` directory
4. securing copy files from your VPS using the following command `scp remote_username@10.10.0.2:~/urbit/sampel-palnet.tar.gz ~/urbit`
5. Uncompress the tarball with the command `tar -xzvf sampel-palnet.tar.gz`
6. Delete the tarball by running `rm -rf sampel-palnet.tar.gz`
7. Run your urbit worker process using `./urbit-worker meld sampel-palnet`
8. Recreate a tarball with the command `tar -czvf sampel-palnet.tar.gz /path/to/pier`
9. Push the compressed pier back into your virtual server by running `scp sampel-palnet.tar.gz remote_username@10.10.0.2:~/urbit/`

## While ssh'd into your VPS
10. Uncompress the tarball with the command `tar -xzvf sampel-palnet.tar.gz`
11. Delete the tarball by running `rm -rf sampel-palnet.tar.gz`
12. Reboot your urbit with `./urbit sampel-palnet` (along with any specific flags for ames/UDP ports or other things)


## General notes
The scp command syntax take the following form:
`scp [OPTION] [user@]SRC_HOST:]file1 [user@]DEST_HOST:]file2`
