## HTTP Questions

__URLs__

* Name all of the parts of the url that you can remember.  In your own words describe what they do.

```
path, protocol, query, anchor, port, domain
```

* Name the pieces of the following urls:
	* `https://www.google.com/`
	* `https://workbook.galvanize.com/cohorts/41/learning_experiences/367`
	* `http://locahost:5000/animals/puppies?onlycute=1&size=medium#firstpuppy`
	* `https://en.wikipedia.org/wiki/List_of_HTTP_status_codes#4xx_Client_Error`
* Can a server use more than 1 port?

```
Yes.
```


* Why is https different than http?

```
It's Secure(TM)!
```


* How does a server interpret the following url's query paramter.  What data structure does it create on the server?

```
http://locahost:5000/animals?puppies=fido&puppies=max&puppies=moxie
```

```
It creates an array from the three values.
```


__HTTP Request/Response__

* Name at least 4 http verbs

```
GET, POST, SEND, DELETE
```

* What is each verb useful for in your own words

```
GET is for, well, GETting a a resource from a server. DELETE deletes resources. POST submits info to a server that alters its state in some way. PUT updates information already on a server.
```

* What does idempotent mean?

```
You can make the same request multiple times without changing anything and you get the same result.
```

* Name the 5 http status code ranges.  What are they used for in general?

```
1XX: What you want is on the way.
2XX: You got waht you requested. All is good.
3XX: What you want is somewhere else.
4XX: Your request was denied because you (the client) messed up.
5XX: Your request was denied because I (the server) messed up.
```


* If a server returns a http status code of 301 and a location of `https://www.google.com/`, what does the browser do?

```
It will redirect you to Google.
```

* For the following HTTP headers, decide if the following header is used for requests, responses or both:
	* Accept `Requests`
	* Content-type `Requests and Responses`
	* User-agent `Requests`
	* Set-cookies `Responses`
	* Cache-control `Requests`
	* Cookie `Responses`
* Is the following a http request or response?  How do you know for each?

```
HTTP/1.1 200 OK
Access-Control-Allow-Origin: *
Vary: Accept
Content-Type: text/html; charset=utf-8
Content-Length: 722
ETag: W/"2d2-Wu0We9N5g35FXWY+gOATLA"
Date: Tue, 08 Mar 2016 20:37:11 GMT
Connection: keep-alive

<!DOCTYPE html>
<html>
  <head>
    <meta charset="utf-8">
    <link rel="stylesheet" href="/style.css">
    <title>Student Roster</title>
  </head>
  <body>
    <main>
      <h1>Student Roster</h1>
      
        <section>
          <h3>Daenerys Targaryen</h3>
          <span>Student Id: nys8fbohl</span>
          <h4>Hobby: Motherhood</h4>
          <img src="https://i.imgur.com/KlycRG5.jpg" alt="Daenerys Targaryen" />
        </section>
      
        <section>
          <h3>Tyrion Lannister</h3>
          <span>Student Id: njehukbohe</span>
          <h4>Hobby: Traveling</h4>
          <img src="https://i.imgur.com/fFMusdC.png" alt="Tyrion Lannister" />
        </section>
      
    </main>
  </body>
</html>
```

```
This is a response. The HTTP 200 OK code lets you know the server has sent what was requested.
```

```
DELETE /students/n1vmyrw3x HTTP/1.1
Host: g22-students.herokuapp.com
Accept: application/json
Cache-Control: no-cache
Postman-Token: 0041e3c3-efdb-f0c3-b2f4-2d79f6d0f44b
```

```
This is a request. You can tell from the DELETE verb, which is requestion the server delete something on its end.
```


__JSON__

* Describe what JSON is.  What is it used for.

```
JSON is JavaSript Object Notation. It's the data exchange format for the web. It's essentially a string that represents arrays and objects in JavaScript.
```

* Convert the following map into a javascript object then console log the age.

```
{ "company" : "Github", "age": 7, "categories" : "Services,Internet,Software"}
```

```
var jsonObj = JSON.parse('{ "company": "Github", "age": 7, "categories": "Services,Internet,Software"}');
console.log(jsonObj.age);
```
* Convert the following to a javascript object.  Console log each company name.

```
{ "Companies":[ { "company": "Github", "age": 7, "categories": "Services,Internet,Software"},
              { "company": "Airbnb", "age": 6, "categories": "Hotels,Travel"},
              { "company": "Square", "age": 7, "categories": "FinTech,Hardware + Software,Finance"},
              { "company": "Dropbox", "age": 11, "categories": "Cloud Data Services,Storage,Web Hosting"}
            ]
}
```

```
var jsonComps = JSON.parse('{ "Companies":[ { "company": "Github", "age": 7, "categories": "Services,Internet,Software"}, { "company": "Airbnb", "age": 6, "categories": "Hotels,Travel"}, { "company": "Square", "age": 7, "categories": "FinTech,Hardware + Software,Finance"}, { "company": "Dropbox", "age": 11, "categories": "Cloud Data Services,Storage,Web Hosting"}]}');

```


```
var jsonObj = JSON.parse('{ "company": "Github", "age": 7, "categories": "Services,Internet,Software"}');
jsonComps.Companies.forEach(function(val){
  console.log(val.company);
});
```

* The following is javascript.  Convert the object to a string and console log it.

```
var myObj = {
  company: "Galvanize",
  age: 3,
  categories: "Education"
};
```

```
console.log(JSON.stringify(myObj));
```


__MISC__

* Describe what DNS is.
* In the terminal, type `man curl`.  Look at the man page for curl.  What do the following flags do? `-v`, `-X`.  (Hint: to search for a string, type `/` then the text you want, then enter.  To quit the man page, type `q`).
* What is TCP/IP?  How does it interact with HTTP?
* Does HTTP break the data that is being sent into small packets?  If not, what protocol is responsible for it?
