# Software Architecture Recovery of Requests

## Context

Requests is a simple, yet elegant, HTTP library written in Python that allows you to send HTTP/1.1 requests extremely easily. It is one of the most downloaded Python packages.     Requests officially supports Python 3.7+, and runs great on PyPy.

### Technical Context

#### Usability

Most existing Python modules for sending HTTP requests are extremely verbose and cumbersome. Python's builtin urllib2 module provides most of the HTTP capabilities you should need, but the api is thoroughly broken. It requires an enormous amount of work (even method overrides) to perform the simplest of tasks. What's more, those modules' documentation is simple and hard to read while their source codes are hard to understand either.

#### Augmentability

Most existing Python modules for sending HTTP requests weren't able to handle the GET/POST ... methods in complex application scenarios. They may be hard to process the sent and received requests.


## Features

### Request

The python requests library has easy to use methods available to handle Http request. Passing of parameters and handling the request type like GET, POST, PUT, DELETE, etc. is very easy.

### Response

You can get the response in the format you need and the supported ones are text format, binary response, json response, and raw response.

### Headers

The library allows you to read, update or send new headers as per your requirements.

### Timeouts

Timeouts can be easily added to the URL you are requesting using python requests library. It so happens that you are using a third-party URL and waiting for a response.
It is always a good practice to give a timeout on the URL as we might want the URL to respond within that timeout with a response or an error that is coming because of timeout. Not doing so can cause either to wait on that request indefinitely.

### Error handling

The requests module gives support for error handling and some of which are Connection Error, Timeout errors, TooManyRedirects, Response.raise_for_status errors, etc.

### Cookies

The library allows you to read, write and update for the requested URL.

### Sessions

To maintain the data, you require between requests you need sessions. So, if the same host is called again and again you can re-use the TCP connection which in turn will improve the performance.

### SSL certificates

SSL certificate is a security feature that comes with secure urls. When you use Requests, it also verifies SSL certificates for the https URL given. SSL Verification is enabled by default in the requests library and will throw an error if the certificate is not present.

### Authentication

HTTP authentication is on the server-side asking for some authentication information like username, password when the client requests a URL. This is an additional security for the request and the response being exchanged between the client and the server.


## Quality Attributes

### Usability

Requests is designed to be the simplest way possible to make http calls. It supports HTTPS and follows redirects by default. It abstracts the complexities of making requests behind a beautiful, simple API.

```python
>>> import requests
>>> r = requests.get('https://httpbin.org/basic-auth/user/pass', auth=('user', 'pass'))
>>> r.status_code
200
>>> r.headers['content-type']
'application/json; charset=utf8'
>>> r.encoding
'utf-8'
>>> r.text
'{"authenticated": true, ...'
>>> r.json()
{'authenticated': True, ...}
```

### Performance

Requests supports streaming uploads, which allow you to send large streams or files without reading them into memory and thanks to urllib3, keep-alive is 100% automatic within a session which improve performance.

### Security

The security is also taken care of the help of authentication module support.When makeing request, the request is made to the URL given and it could be a secure or non-secure URL.


## Key Drivers

### Usability

Requests is designed to be the simplest way possible to make http calls which is easy to get started.

### High Augmentability

Requests welcomes other contributors to update or advance content.

## Earliest Design Decisions

* Requests should be BDFL(Benevolent Dictator For Life), which when other contributors make contribution to the project, founders will consolidate all resources to build up requests.
* Requests should be able to supports Python 2.6-2.7 and 3.x, and can should perfectly in PyPy. These editions are the most used today.
* Requests should be flexible, which we should insert a hook system in the project. The hook system is most often used in some process processing. This process often has many steps. These hook functions are often mounted in these steps to provide flexibility for adding additional operations. However, it may be hard to prepare and write.
* Requests should be simple to use, which we should encapsulate the http methods one by one in the API. It may be cockamamie to realise but benifit the structure of our code.

#### The first decision is the leadership strategy of Requests. The other three decisions are the basic requirement of Requests.


## Key StakeHolders

### Business Manager

Responsible for the functioning of the business/organizational entity that owns the system. Includes managerial/executive responsibility, responsibility for defining business processes, etc.

#### Concerns:
* Requests should be simpler and easier to use and understand than other Python modules for sending HTTP requests.
* Requests should be open.

### Integrator

Responsible for taking individual components and integrating them, according to the architecture and system designs.

#### Concerns:
* Each components or parts of Requests should be neat and clear.

### Customer

Pays for the system and ensures its delivery. The customer often speaks for or represents the end user, especially in a government acquisition context.

#### Concerns:
* Requests should be easy to use and have exhaustive documentation for guiding.
* Requests should be stable and not changes often.
