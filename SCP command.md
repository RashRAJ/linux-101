# Using the SCP Linux command
The scp tool relies on SSH (Secure Shell) to transfer files, so all you need is the username and password for the source and target systems. Another advantage is that with SCP you can move files between two remote servers, from your local machine in addition to transferring data between local and remote machines. In that case you need usernames and passwords for both servers

## 1) Copy a single file from the local machine to a remote machine:
The scp command needs a source and destination to copy files from one location to another location. This is the pattern that to use:

``` scp localmachine/path_to_the_file  username@server_ip:/path_to_remote_directory ```

## Copy a local directory to a remote server:
If you want to copy the entire local directory to the server, then you can add the -r flag to the command:

``` scp -r localmachine/path_to_the_directory username@server_ip:/path_to_remote_directory/ ```

To copy all the files inside a local directory to a remote directory?  simply, just add a forward slash and * at the end of source directory and give the path of destination directory. Don’t forget to add the -r flag to the command:

``` scp -r localmachine/path_to_the_directory/* username@server_ip:/path_to_remote_directory/ ```

## 2) Copying files from remote server to local machine
If you want to make a copy of a single file, a directory or all files on the server to the local machine, just follow the same example above, just exchange the place of source and destination.

### Copy a single file:

``` scp username@server_ip:/path_to_remote_directory local_machine/path_to_the_file ```

### Copy a remote directory to a local machine:

``` scp -r username@server_ip:/path_to_remote_directory local-machine/path_to_the_directory/ ```

Make sure that the source directory doesn’t have a forward slash at the end of the path, at the same time the destination path *must* have a forward slash.

### Copy all files in a remote directory to a local directory:

``` scp -r username@server_ip:/path_to_remote_directory/* local-machine/path_to_the_directory/ ```

## 3) Copy files from one remote server to another remote server from a local machine.

### Copy a single file:
``` scp username@server1_ip:/path_to_the_remote_file username@server2_ip:/path_to_destination_directory/ ```

### Copy a directory from one location on a remote server to different location on the same server:

```scp username@server1_ip:/path_to_the_remote_file username@server2_ip:/path_to_destination_directory/ ```

### Copy all files in a remote directory to a local directory

```scp -r username@server1_ip:/path_to_source_directory/* username@server2_ip:/path_to_the_destination_directory/ ```
