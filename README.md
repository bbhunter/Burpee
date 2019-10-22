# Burpee
## About
A python module to extract headers and POST data from a file containing intercepted HTTP request.

Let's say we have a file named <b>request.txt</b> that contains following HTTP request:
```
POST /user/follow HTTP/1.1
Host: www.website.com
User-Agent: some user agent
Accept: application/json, text/plain, */*
Accept-Language: pl,en-US;q=0.7,en;q=0.3
Referer: https://www.website.com/users/12345/profile
Content-Type: application/json;charset=utf-8
X-CSRF-TOKEN: Ab1/2cde3fGH
Content-Length: 27
Cookie: some-cookie=;
DNT: 1
Connection: close

{"targetUser":"12345"}
```
To send the above request using inbuilt functions of python like requests.get(), we need to explicitely specify each of the headers and values manually.

Here <b>Burpee</b> comes to save the day. It simply accepts name of the file containing the HTTP request as parameter and returns two things:
* Dictionary: Headers and their respective values 
* String: Supplied Post data

## Screenshot:
<img src="media/screenshot.png"/>

## Demonstration:
<img src="media/demonstration.gif">

As demonstrated in the above proofs, once we get dictionary of headers and post data, we can simply pass these headers and post data to functions like requests.get() , requests.post() etc.

Request can be directly requested by using the <b>request()</b> function in the module.<br> <b>Burpee.burpee.request(<i>file_name</i> , <i>https = </i>[True/False])</b> takes two arguments:
* Name of the file containing request
* Whether to request HTTP or HTTPS

Since this function uses requests.get() and requests.post() from inside, hence it also returns the <b>
requests.models.Response</b> object.

### [NOTE]:
The request() function only supports two methods i.e. GET and POST

### Creator: 
Twitter: <a href="https://twitter.com/xscorp7">@xscorp7</a><br>
Github: <a href="https://github.com/xscorp">xscorp(GITHUB)</a>
