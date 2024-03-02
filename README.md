# veracrypt_remote_mount
Custom made script for decrypting volumes encrypted by veracrypt.  
To protect drives attached to my raspberry pi, I encrypted them using veracrypt.  
But I set up weekly backups of the pi to be stored in one of the drives.  

One easy solution is to auto-mount them on every reboot, which is not very secure.  
So, I decided to design a webpage from which I can take password as input and decrypt the drives only when I need.  

In veracrypt_mount.sh, change the mount points and device paths as required.  
When the script is run, it displays the index.html file inside templates folder.  
Entering the password in the form and submitting it will verify if the password works for the drive you provided in the shell script.  
There is also an option to protect hidden volume by providing the hidden volume's password. If there is no hidden volume, leave that field blank.  
In case of errors, they will be written to mount_fail.log.

Now, this script only runs this service on local network. So, if you're out of that network, you can't decrypt the drives.  
To solve this I used ngrok. Check out how to host a website using ngork in my notes [here](https://suchitreddi.github.io/Work/self_site.html).  
I provided sample ngrok files in this repository. These should be enough for you to access the page from the open internet and decrypt your drives remotely.  
To check if the script is running, and run it if it isn't, we add this following line at the end of "crontab -e"  
`* * * * * /usr/bin/python3 /path/to/veracrypt_mount.py`  

Contact me at [suchit20016+veremou@gmail.com](mailto:suchit20016+veremou@gmail.com) if you have any queries or concerns regarding the script.
