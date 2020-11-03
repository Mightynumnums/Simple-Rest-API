# The repo belongs to Aditya Sridhar. I've simply added the steps from the blog straight into this repo for ease of running basic cURL commands.

---

# Building REST apis with Nodejs without using any framework or external library

This Repo is part of a blog.

The link to the blog is [https://adityasridhar.com/posts/how-to-use-nodejs-without-frameworks-and-external-libraries](https://adityasridhar.com/posts/how-to-use-nodejs-without-frameworks-and-external-libraries)

## Pre-requisite

Ensure You have NodeJS installed in your system.
Refer to [https://nodejs.org](https://nodejs.org) to install NodeJS

## Cloning and Running the Code

This code can be cloned to your local using the command

```
git clone https://github.com/aditya-sridhar/simple-rest-apis-nodejs-without-frameworks.git
```

cd into the repo and make sure to install all the needed dependencies

```
npm i
```

or

```
npm install
```

## Running the code

`server.js` is the starting point of the code

The application can be started using the command

```
node server.js
```

### Thank you Aditya Sridhar for the repo.

---

Extra Details to get the commands and the cURL to work:

Follow the steps above to start the server.

Once the server is running, in a new terminal window, or tab:

```
curl http://localhost:3000/sample?name=yourName
```

you should see

```
{"text":"Hello yourName"}%
```

## cURL with verbose output

Then you can also run the cURL command in a verbose mode:

```
curl -v http://localhost:3000/sample?name=yourName
```

which should result in something like:

```
    *Trying ::1...
    * TCP_NODELAY set
    * Connection failed
    * connect to ::1 port 3000 failed: Connection refused
    *   Trying 127.0.0.1...
    * TCP_NODELAY set
    * Connected to localhost (127.0.0.1) port 3000 (#0)
    > GET /sample?name=Aleks HTTP/1.1
    > Host: localhost:3000
    > User-Agent: curl/7.64.1
    > Accept: */*
    >
    < HTTP/1.1 200 OK
    < Content-Type: application/json
    < Date: Tue, 03 Nov 2020 21:30:07 GMT
    < Connection: keep-alive
    < Content-Length: 22
    <
    * Connection #0 to host localhost left intact
    {"text":"Hello yourName"}* Closing connection 0
```

#### -v is used to get verbose output

## POST request with cURL

In your terminal window, run:

```
curl --header "Content-Type: application/json" -d "{\"value\":\"node JS\"}" http://localhost:3000/test
```

expected output:

```
{"text":"Post Request Value is  node JS"}%
```

–header indicates the content type of the post body. Here it is JSON.
-d is used to send the post body content.

-   You can also run a verbose command like so

```
curl -v --header "Content-Type: application/json" -d "{\"value\":\"node JS\"}" http://localhost:3000/test
```

## MORE

Additional Options provided by command line could be found in the documentation **[HERE](https://ec.haxx.se/)**
