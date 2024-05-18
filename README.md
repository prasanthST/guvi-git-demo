# HTTP/1.1 vs. HTTP/2: A Speed Showdown for the Modern Web

| HTTP/1.1 | HTTP/2 | 
|----------|----------|
| It works on the textual format.     | It works on the binary protocol.
| There is head of line blocking that blocks all the requests behind it until it doesn’t get its all resources.	  | It allows multiplexing so one TCP connection is required for multiple requests.|
| It uses requests resource Inlining for use getting multiple pages	 | It uses PUSH frame by server that collects all multiple pages |
| It compresses data by itself.	 | It uses HPACK for data compression.|

## HTTP/1.1
* let’s assume the situation when you make a request to the server for the Google.html page & server responds to you as a resource Google.html page.
* before sending the request and the response there is a TCP connection established between client & server.
* again you make a request to the server for image img.jpg & the server gives a response as an image img.jpg.
* the connection was not lost here after the first request because we add a keep-alive header which is the part of the request so there is an open connection between the server & client.  & responses are merged in a single connection.
## HTTP/2
* HTTP/2 was developed over the SPDY protocol.
* HTTP/2 works on the binary framing layer instead of textual that converts all the messages in binary format.
* it works on fully multiplexed that is one TCP connection is used for multiple requests.
* HTTP/2 uses HPACK which is used to split data from header. it compresses the header.
* The server sends all the other files like CSS & JS without the request of the client using the PUSH frame.
### Disadvantage
* These are the drawbacks that lead to the creation of HTTP/2: The first problem is HTTP/1.1 transfer all the requests & responses in the plain text message form.
* The second one is head of line blocking in which TCP connection is blocked all other requests until the response does not receive.
*  all the information related to the header file is repeated in every request.
