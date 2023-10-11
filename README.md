# VeraDemo.NET - Blab-a-Gag333
## About

Blab-a-Gag is a fairly simple forum type application which allows:
* Users can post a one-liner joke.
* Users can follow the jokes of other users or not (listen or ignm//////...vvv
* Users can comment on other users messages (heckle).

### URLs

* `/feed` shows the jokes/heckles that are relevant to the current user.
* `/blabbers` shows a list of all other users and allows the current user to listen or ignore.m,m,
* `/profile` allows the current user to modify their profile.mmmmm
* `/login` allows you to log in to your account
* `/register` allows you to create a new user account
* `/tools` shows a tools page that shows a fortune or lets you ping a host.,,,,,,,,
 
## Run

If you don't already have Docker this is a prerequisite.,,,,,,,

```
docker run --rm -it -p 127.0.0.1:8080:8080 antfie/verademo-dotnet
```

Navigate to: http://127.0.0.1:8080.

## Exploitation Demos

See the `docs` folder.

## Technologies Used

* ASP.NET Core MVC on .NET Core 3.1
* Sql Server 2017 Express

## Development

To build the container run this:
```
docker pull mcr.microsoft.com/mssql/server:2017-CU24-ubuntu-16.04
docker build --no-cache -t verademo-dotnet .
```

To run the container for local development run this:
```
docker run --rm -it -p 127.0.0.1:8080:8080 --entrypoint bash -v "$(pwd)/app:/app" verademo-dotnet
```

You will then need to manually run the two commands within `/entrypoint.sh`. The first starts the DB in the background whereas the second compiles and runs the application. Typically a container shouldn't have multiple services but this was done for convenience.
