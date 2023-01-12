# SOAP

SOAP is an XML-based protocol for sending and receiving messages over the internet or a local network.
It defines a set of rules for structuring and encoding the messages, as well as a way to indicate the actions to be performed by the receiving system.
An example of a SOAP request and response:

```
POST /InStock HTTP/1.1
Host: www.example.com
Content-Type: application/soap+xml; charset=utf-8
Content-Length: nnn

<?xml version="1.0"?>
<soap:Envelope xmlns:soap="http://www.w3.org/2001/12/soap-envelope"
soap:encodingStyle="http://www.w3.org/2001/12/soap-encoding">
  <soap:Body xmlns:m="http://www.example.com/stock">
    <m:GetStockPrice>
      <m:StockName>IBM</m:StockName>
    </m:GetStockPrice>
  </soap:Body>
</soap:Envelope>
```


- Pros:
	- SOAP provides a lot of built-in security features like WS-Security, WS-ReliableMessaging and WS-AtomicTransaction which makes it ideal for sensitive and mission-critical data.
	- SOAP is platform and language independent, which means it can be used in any environment regardless of the programming language.
	- SOAP provides built-in error handling, which makes it easy to detect and correct errors.
- Cons:
	- SOAP is more complex than REST and can be more difficult to implement.
	- SOAP requires more bandwidth than REST, which can be a problem for low-bandwidth connections.
	- SOAP can be less performant than REST.

# REST

REST is an architectural style for building web services that uses standard HTTP methods (such as GET, POST, PUT, and DELETE) to retrieve or modify data.
It does not define a specific format for the messages, so any format can be used, such as XML or JSON.
An example of a REST request and response:

```
GET /stock/IBM HTTP/1.1
Host: www.example.com
Accept: application/json

HTTP/1.1 200 OK
Content-Type: application/json

{
    "stockName": "IBM",
    "price": "120.5"
}
```

- Pros:
	- REST is simple and easy to implement.
	- REST uses less bandwidth than SOAP, which makes it more efficient for low- bandwidth connections.
	- REST is more performant than SOAP.
- Cons:
	- REST does not provide as many built-in security features as SOAP, which can be a problem for sensitive and mission-critical data.
	- REST is not as platform and language independent as SOAP, as it is usually used with HTTP and JSON.
	- REST does not provide built-in error handling, which can make it more difficult to detect and correct errors.

## Making RESTful API

https://www.redhat.com/en/topics/api/what-is-a-rest-api

REST is a set of architectural constraints, not a protocol or a standard. API developers can implement REST in a variety of ways.

When a client request is made via a RESTful API, it transfers a representation of the state of the resource to the requester or endpoint. This information, or representation, is delivered in one of several formats via HTTP: JSON (Javascript Object Notation), HTML, XLT, Python, PHP, or plain text. JSON is the most generally popular file format to use because, despite its name, it’s language-agnostic, as well as readable by both humans and machines.

Something else to keep in mind: Headers and parameters are also important in the HTTP methods of a RESTful API HTTP request, as they contain important identifier information as to the request's metadata, authorization, uniform resource identifier (URI), caching, cookies, and more. There are request headers and response headers, each with their own HTTP connection information and status codes.

In order for an API to be considered RESTful, it has to conform to these criteria:

-   A client-server architecture made up of clients, servers, and resources, with requests managed through HTTP.
-   [Stateless](https://www.redhat.com/en/topics/cloud-native-apps/stateful-vs-stateless) client-server communication, meaning no client information is stored between get requests and each request is separate and unconnected.
-   Cacheable data that streamlines client-server interactions.
-   A uniform interface between components so that information is transferred in a standard form. This requires that:
    -   resources requested are identifiable and separate from the representations sent to the client.
    -   resources can be manipulated by the client via the representation they receive because the representation contains enough information to do so.
    -   self-descriptive messages returned to the client have enough information to describe how the client should process it.
    -   hypertext/hypermedia is available, meaning that after accessing a resource the client should be able to use hyperlinks to find all other currently available actions they can take.
-   A layered system that organizes each type of server (those responsible for security, load-balancing, etc.) involved the retrieval of requested information into hierarchies, invisible to the client.
-   Code-on-demand (optional): the ability to send executable code from the server to the client when requested, extending client functionality.

