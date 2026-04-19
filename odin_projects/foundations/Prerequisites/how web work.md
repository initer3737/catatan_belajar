## how internet works

### summary
- internet is backbone of the web
- internet is a large network of computer which comunicate all together



  ### history
  - it began 1960 as a us-army funded research project , them evolved into a public infrastructure in the 1980s with the support of many public universities and private companies. The various technologies that support the Internet have evolved over time, but the way it works hasn't changed that much: Internet is a way to connect computers all together and ensure that, whatever happens, they find a way to stay connected.



### internet
- wire/fiber optic that burried in the ground


### client
- computer or device that initiate request /get access to the data from internet/servers

### ip address
- device that identified uniquely and it like home address in simple understanding
- server can have ip address
- but not all human can memorize ip address
- domain name come to solve human weakness like youtube.com

### dns
- domain name system is a phonebook translating compleks ip address into easy to remember web address like yotube.com in order to make human understand/easey to memorize ip adress of some website 

### isp
- internet service provider 
- company that provide individuals and business access to the internet
- they offer conectivity throught tecnologies like fiber optice cable dsl/ or satelite

### dsl
- DSL (Digital Subscriber Line) internet is _a broadband service that delivers high-speed connectivity through existing copper telephone lines, allowing simultaneous internet use and phone calls_. It operates via a modem, providing an "always-on" connection that is generally faster than dial-up but slower than fiber or cable.
- tecnology data sender via internet signal, using telephone cable/line

### package 
- package is something like image that send to  someone and internet break it to smaller pieces  called package and asemble it in one image full  

### server
 - powerfull computer the job is to provide you something like webpage or video
   
### router
- A router is _a networking device that acts as a traffic controller, directing data packets between different networks_—typically between your local home/office network (LAN) and the internet (WAN). It enables multiple devices (phones, computers, smart TVs) to share a single internet connection provided by a modem.
- internet device that connecting your device to the internet  


### data center
- send to the satelite and send it to mobile phone but not good idea because the data must travel 44 mile or more and it is long 
- so optical fiber network come to solve this problem

### optical fiber
- is used to make internet works
- it is backbone of the internet
- carying the light and connected to router then it translate  the light to electric signal
- ethernet cable is then used to transmit the electrical signal to yout laptop
- if u are using phone optical cable is then has to be sent to a cell tower and then the signal come to your phone form of electromagnetic waves
- ICANN organization to managing the Domain Name System (DNS) and allocating IP addresses to keep the internet reachable

### bandwith
- maximum capacity of an internet connection to transfer data between device and internet within specific time frame it can be mbps,kbps etc
- upstream/upload downstream/download
- kecepatan maksimum yang bisa ditransfer oleh device user dalam waktu tertentu
- menentukan kecepatan jaringan user dalam mengakses ,mendownload kontent yang ada di internet

### switch
- allow multipple device to be connected within a local area network/lan 

### router vs switch
- router connect 1 network to the internet
- switch connect multiple device into an lan/local area network
  
#### web page
- document can displayed in a web browser and written in html mark up language
  
#### website
- collection of web page grouped together into a single resource with link connecting them together
  #### web server
  - computer that hosts a website on the internet
    
#### web service
- is like API aplication programming interface, program that responds to the request 
- A software that responds to requests over the Internet to perform a function or provide data. A web service is typically backed by a web server, and may provide web pages for users to interact with

  #### search engine
  - web service that help you to find other web pages such as google bing and duck duck go
  
### web page website web server and search engine

#### url 
- uniform resource locator, text string that specifies where a resource can be found in the internet like web page image or video
  - are commonly called web addresses or links
    
 #### browser vs search engine
 - browser is a piece of software that retrieves and display web pages
 - search engine is a web service(and usually a website) that help people find web pages contained on other website
    ![alt text](https://developer.mozilla.org/en-US/docs/Learn_web_development/Getting_started/Environment_setup/Browsing_the_web/search-engine.jpg)







#### web browser
- software that help you to find a web page
- aplication that allow you to visit website

#### how web work
- clients and servers
    - computer connected to the internet are called client and servers
    - clients is device connected to the internet to get data from server
    - server is computer to provide data from clients request
              ![image diagram](https://developer.mozilla.org/en-US/docs/Learn_web_development/Getting_started/Web_standards/How_the_web_works/simple-client-server.png)          
     - server: computer that send my own device a data that i want to request
       - client : device that i use to access the internet

***
  - **your internet connection** : allow yout to send and recieve data from the internet
  - **tcp/ip** : transmission control protocol and internet protocol or tcp/ip comunication protocols that define how data should travel across the internet 
- **DNS** : domain name system is like address for the website , the browser always look at the dns to find website ip adress  
- **http:hypertext transfer protocol** is an application protocol that defines a language for clients and server to speak each other
  
### behind the scene
- the browser goes to the dns server and find the real address of the server that website lives on
- browser send an http request message to the server asking it to send a copy of website to the client, this message and all other data sent between the client and the server , is sent across your internet connection using tcp/ip
- if the server approves the client's request the server send the clients a 200 ok message which "mean of course you can look at that website here it is" and then start sending the website's files to the browser as a series of small chunks called packets.
- the browser assembles the small chunks into a complete web page and display it yo you 

## **dns explained**
- real web address or uniform resource locator are not memorable by human likely like this 192.0.2.172 it called ip adress and it is not good to memorize by human so dns come in dns is like youtube.com ,that is very easy to human to memorize
- this system is uses special servers that match up a web address like type in uniform resource locator like youtube.com to the website real ip adress 


## **packets explained**
- when data is sent acrross the web it is sent in multiple small chunks called packets each packet contain
- a **header** which includes details such as the server and the client ip adress the packet number ,the total number of packets in the transmission and details of the protocols used in transmission
-  a **payload** which contain the actual data sent in the packet.


 ### **reason behind it / why data sent in small packets**
- they sometimes dropped or corrupted and when this happens it's quicker and easier for the client to request the missing packets rather than an entire file
- the packet can be routed along different paths, making the transmission as efficient as possibility of slowing donw the network especially when many user are requesting the same resource simultaneously, the packets may arrive out of sequence , but the client can use the information in the packet header to make sure they are assembledin the correct order

  ***
  ### HTTP basic

        get verb
      GET /en-US/ HTTP/2
        Host: developer.mozilla.org
            response to get verb
            HTTP/2 200

        date: Tue, 11 Feb 2025 11:13:30 GMT
        expires: Tue, 11 Feb 2025 11:40:01 GMT
        server: Google frontend
        last-modified: Tue, 11 Feb 2025 00:49:32 GMT
        ETag: "65f26b7f6463e2347f4e5a7a2adcee54"
        content-length: 45227
        content-type: text/html
        
        <!doctype html> ... (the 45227 bytes of the requested web page HTML)
  - http uses a simple language of verb to perform action such as making requests . the http get method is the one normally used to make http requests of the type described above 
    

|  code |  mean |  status |
|---|---|---|
|  200 |  okay |  successful |
|   301   |    permanently moved   |             |
|     404    |            cannot find the requested resource            |       not found      |
|   400   |    The server can't process the request. This usually happens when the request isn't in a format the server understands, or has errors in it.   |             |
|  403 |  dont have permission to acces the file |   |
|   503   |                     The request cannot be handled due to a problem with the server. This is common when servers are offline for maintenance, and it's expected to be temporary.                    |  server error |

***
 ### component of uniform resource locator a.k.a url

***
## sources 
[mdn how internet work](https://developer.mozilla.org/en-US/docs/Learn_web_development/Howto/Web_mechanics/How_does_the_Internet_work#summary)
[computer work in 5 minuta](https://youtu.be/7_LPdttKXPc)
[dsl revou](https://www.revou.co/kosakata/dsl)
[bandwidth](https://www.revou.co/kosakata/bandwidth?_gl=1*duq829*_gcl_au*MTM5MDAxMjAxOC4xNzc2NjI2MzQ3)
[switch](https://olin.es/en/blog/what-is-a-network-switch/)
[different web page by mdn](https://developer.mozilla.org/en-US/docs/Learn_web_development/Getting_started/Environment_setup/Browsing_the_web)
[url](https://developer.mozilla.org/en-US/docs/Glossary/URL)
[how web work last ](https://developer.mozilla.org/en-US/docs/Learn_web_development/Getting_started/Web_standards/How_the_web_works#clients_and_servers)