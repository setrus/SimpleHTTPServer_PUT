## SimpleHTTPServer with PUT method
SimpleHTTPServer from Python that accespts *PUT* HTTP method. 
</br>
Python Module for SimpleHTTPServer does not allow PUT method. Using this server, you can exfiltrate data to the server running on the attacker machine

</br> **Example**
Uploading a simple file *test.file* to the HTTP server. Content of the file:
```
┌──(kali㉿kali)-[~]
└─$ cat test.file
Upload Successful
```
1 Starting the server 
```
┌──(kali㉿kali)-[~/tools/SimpleHTTPServer_PUT]
└─$ python2 HTTPServer_PUT.py
Serving HTTP on 0.0.0.0 port 8000 ...
```
2 Sending the file 
```                                                                                                                    
┌──(kali㉿kali)-[~]
└─$ curl http://localhost:8000 --upload-file test.file
curl: (52) Empty reply from server
```
3 Receiving the file
```
┌──(kali㉿kali)-[~/tools/SimpleHTTPServer_PUT]
└─$ python2 HTTPServer_PUT.py
Serving HTTP on 0.0.0.0 port 8000 ...
Host: localhost:8000
User-Agent: curl/7.79.1
Accept: */*
Content-Length: 18
Expect: 100-continue

^C
KeyboardInterrupt
                                                                                                                    
┌──(kali㉿kali)-[~/tools/SimpleHTTPServer_PUT]
└─$ ls                                                                                                          1 ⨯
HTTPServer_PUT.py  README.md  test.file
                                                                                                                    
┌──(kali㉿kali)-[~/tools/SimpleHTTPServer_PUT]
└─$ cat test.file 
Upload Successful

```
