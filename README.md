# Backend Hello World

This repo contains the general requirements and description of a simple API project intended to evaluate a Backend Developer candidate.

## Objective

Your task is to create a RESTful API server for the registration, login, logout and status of fake users. 

## Endpoints

Your system must serve the following endpoints:

- `/register`: user/password request that creates a user in the system's database. When we say *database* we mean a simple table in volatile memory, not an actual database storage entity. When we turn off the server, we expect to lose track of the users registered at the time it was on.

- `/login`: user/password request, token-based authentication for granted users.

- `/logout`: token-based request, and token revocation.

- `/status`: token-based request, overall system status.

## Test Cases

Below you will see some examples of input and output on how your program will be tested:

- **Register**

```
$ curl -u username:password http://localhost:8080/register
{
    "message": "User created successfully."
}
```

- **Login**

```
$ curl -u username:password http://localhost:8080/login
{
    "message": "Hi <username>, welcome to the API system",
    "token": "OjIE89GzFw"
}
```

- **Logout**

```
$ curl -H "Authorization: Bearer <ACCESS_TOKEN>" http://localhost:8080/logout
{
	"message": "Bye <username>, your token has been revoked"
}
```

*Note: a revoked token means that the token can be used again without turning off the server.*

- **Status**

```
$ curl -H "Authorization: Bearer <ACCESS_TOKEN>" http://localhost:8080/status
{
	"message": "Hi <username>, the API system is up and running
	"time": "2015-03-07 11:06:39"
}
```

*Note: this is an endpoint for the server status, and must always send the same message lol.*

## Requirements

We encourage you to use:

- Java programming language.

- a public repository to store your app. Make sure you send us the link.

- the English language for your code names, documentation and comments.

- a README.md file with the **set up instructions and version requirements** in your repository so that we can understand **how to run your code**. Please write it assuming we do not know anything about what your API system does.

*Note: anything not described here can be assumed as you wish.*
