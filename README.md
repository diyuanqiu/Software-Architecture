# Software Architecture Recovery of Requests

## Context

Requests is a simple, yet elegant, HTTP library written in Python that allows you to send HTTP/1.1 requests extremely easily. It is one of the most downloaded Python packages.     Requests officially supports Python 3.7+, and runs great on PyPy.


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

### High Expansibility

Requests welcomes other contributors to update or advance content.

## Earliest Design Decisions

1. Requests should be BDFL(Benevolent Dictator For Life), which when other contributors make contribution to the project, founders will consolidate all resources to build up requests.
2. Requests should be able to handle concurrency problems.
3. Requests should be able to support python 3.x .
4. Requests should have exhaustive unit tests.

##### The first decision is the leadership strategy of Requests. The other three decisions are the basic requirement of Requests.
