# HTTP Response Status Codes

Status codes are issued by a server in response to a client's request made to the server. It includes codes from IETF RFCs, other specifications, and some additional codes used in common applications of HTTP.

## General Information

- The first digit of the status code specifies one of five standard classes of responses.
- Message phrases are typical but optional.
- Status codes are part of the HTTP standard unless otherwise noted.
- The [IANA](https://www.iana.org/assignments/http-status-codes/http-status-codes.xhtml) maintains the official registry of HTTP status codes.

## Classes of Status Codes

- **1xx Informational** – Request received, continuing process
- **2xx Success** – Request was successfully received, understood, and accepted
- **3xx Redirection** – Further action must be taken to complete the request
- **4xx Client Error** – The request contains bad syntax or cannot be fulfilled
- **5xx Server Error** – The server failed to fulfill a valid request

---

## 1xx Informational Response

- **100 Continue** – Client should continue with request body
- **101 Switching Protocols** – Server is switching protocols
- **102 Processing** *(WebDAV, deprecated)* – Server is processing the request
- **103 Early Hints** – Returns headers before final response

---

## 2xx Success

- **200 OK** – Standard success response
- **201 Created** – Resource created
- **202 Accepted** – Request accepted, processing not complete
- **203 Non-Authoritative Information** – Modified response from a proxy
- **204 No Content** – No content to send
- **205 Reset Content** – Reset document view
- **206 Partial Content** – Partial resource returned
- **207 Multi-Status** *(WebDAV)* – Multi-response (XML)
- **208 Already Reported** *(WebDAV)* – Already included
- **226 IM Used** – Instance manipulations applied

---

## 3xx Redirection

- **300 Multiple Choices** – Multiple options available
- **301 Moved Permanently** – Redirect to new URI
- **302 Found** – Temporarily moved
- **303 See Other** – See another URI (GET)
- **304 Not Modified** – Resource not modified
- **305 Use Proxy** – Must access via proxy
- **306 Switch Proxy** *(unused)*
- **307 Temporary Redirect** – Same method must be used
- **308 Permanent Redirect** – Like 301 but method must not change

---

## 4xx Client Errors

- **400 Bad Request**
- **401 Unauthorized**
- **402 Payment Required** *(Reserved/Various uses)*
- **403 Forbidden**
- **404 Not Found**
- **405 Method Not Allowed**
- **406 Not Acceptable**
- **407 Proxy Authentication Required**
- **408 Request Timeout**
- **409 Conflict**
- **410 Gone**
- **411 Length Required**
- **412 Precondition Failed**
- **413 Payload Too Large**
- **414 URI Too Long**
- **415 Unsupported Media Type**
- **416 Range Not Satisfiable**
- **417 Expectation Failed**
- **418 I'm a teapot** *(Easter egg)*
- **421 Misdirected Request**
- **422 Unprocessable Content**
- **423 Locked** *(WebDAV)*
- **424 Failed Dependency** *(WebDAV)*
- **425 Too Early**
- **426 Upgrade Required**
- **428 Precondition Required**
- **429 Too Many Requests**
- **431 Request Header Fields Too Large**
- **451 Unavailable For Legal Reasons**

---

## 5xx Server Errors

- **500 Internal Server Error**
- **501 Not Implemented**
- **502 Bad Gateway**
- **503 Service Unavailable**
- **504 Gateway Timeout**
- **505 HTTP Version Not Supported**
- **506 Variant Also Negotiates**
- **507 Insufficient Storage**
- **508 Loop Detected**
- **510 Not Extended**
- **511 Network Authentication Required**

---

## Unofficial Codes

Some frameworks or services define additional codes:

- **218 This is fine** *(Apache)*
- **419 Page Expired** *(Laravel)*
- **420 Method Failure** *(Spring)* / **420 Enhance Your Calm** *(Twitter)*
- **430 Request Header Fields Too Large** *(Shopify)*
- **450 Blocked by Windows Parental Controls**
- **498 Invalid Token**, **499 Token Required** *(Esri)*
- **509 Bandwidth Limit Exceeded**
- **529 Site is overloaded**
- **530 Site is frozen / Origin DNS Error** *(Shopify)*
- **540 Temporarily Disabled** *(Shopify)*
- **598 Network read timeout error**
- **599 Network connect timeout error**
- **783 Unexpected Token** *(Shopify)*
- **999 Non-standard (LinkedIn)**

---

## Microsoft IIS Specific Codes

- **440 Login Timeout**
- **449 Retry With**
- **451 Redirect**

---

## nginx Specific Codes

- **444 No Response**
- **494 Request Header Too Large**
- **495 SSL Certificate Error**
- **496 SSL Certificate Required**
- **497 HTTP Request Sent to HTTPS Port**
- **499 Client Closed Request**

---

## Cloudflare Specific Codes

- **520 Web Server Returned an Unknown Error**
- **521 Web Server Is Down**
- **522 Connection Timed Out**
- **523 Origin Is Unreachable**
- **524 A Timeout Occurred**
- **525 SSL Handshake Failed**
- **526 Invalid SSL Certificate**
- **527 Railgun Error (obsolete)**
- **530 Returned with 1xxx**

---

## AWS Elastic Load Balancing

- **000** – Header too large / too many requests
- **460** – Client closed connection before timeout
- **463** – Too many IPs in X-Forwarded-For
- **464** – Incompatible protocol versions
- **561** – Authentication error with IdP

---

## Obsoleted Caching Warning Codes

> These were used in the `Warning` header and obsoleted in RFC 9111 (2022)

- **110 Response is Stale**
- **111 Revalidation Failed**
- **112 Disconnected Operation**
- **113 Heuristic Expiration**
- **199 Miscellaneous Warning**
- **214 Transformation Applied**
- **299 Miscellaneous Persistent Warning**
