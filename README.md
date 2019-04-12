# LFI+phpinfo=RCE
remote code execution with the help of phpinfo and lfi

This script is not my work. 
I modified the script so now it works as intended unlike when I found it.

This script will get remote code execution providing a few factors are in play
1. you have local file inclusion
2. you can see phpinfo being displayed
3. file uploads are set to on in php.ini (this can be tested by looking at the phpinfo after a post request with form data. you should see a tempory file created in the php variables secion of phpinfo.)

This exploits a race condition whereby you will execute code placed in a file uploaded in a post request to the sever. The file has padding to increase the time taken to process the file by the server. If you successfully call the temporary file with lfi it will execute code in the temporary file giving you code execution.  
