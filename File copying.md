# copying files owned by a user and copying a directory

## first list the files in the directory  to identify the user that own the file
 ` ls -l /directory/` or use `ll /directory/ `
 
 ## To find files owned by the user
 `find /home/directory/ -type f -user username`
 
 ## Find the files name by user & copy with folder structure
`find /home/directory/ -type f -user username -exec cp --parents {} /new_directory \;`

## List the files copied in the destination folder
`ll /new_directory/home/directory/`
