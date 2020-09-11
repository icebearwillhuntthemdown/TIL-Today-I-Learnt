# cURL
cURL stands for **Client URL**  
curl is used in command lines or scripts to transfer data to and from a server from shell using multiple protocols including HTTP requests 

## Options
* `curl [url]` :  calling a GET method  
    The output of this command is the whole HTTP response's body the site returns on a GET.  
        `curl http://www.google.com`  
* `--data`, `-d` : doing a POST to a URL  
    - query string  
    `curl --data "name=John&surname=Doe" http://www.google.com` 
    - regular JSON  
    `curl --data '{"name" : "John", "surname" : "Doe"}' \http://www.google.com`

* `-i`, `--head` : requesting request head  
    - `-i` : returns the HTTP response including request header    
    - `--head`, `-I` : only returns request head. The server returns the headers exactly the way it would do for a GET but without a body.  
    `curl --head http://www.google.com`

* `curl [url] [url]` : multiple URLs in a single command line   
    - GET  
    `curl http://www.naver.com http://google.com`

    - OTHERS  
    `curl --data http://www.naver.com http://google.com`  
    using --data to POST to multiple URLs means that you send the same POST to all the given URLs.  

* `--next` : separates commands so that multiple HTTP methods can be executed in a single command line  
    `--next` resets the method and allow a new set  
    `curl -I http://www.google.com --next http://www.google.com`


## References
* [curl](https://curl.haxx.se/docs/)
* [FreeCodeCamp](https://www.freecodecamp.org/news/how-to-start-using-curl-and-why-a-hands-on-introduction-ea1c913caaaa/)
