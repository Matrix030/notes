Servers are interesting because they're _always running._ A lot of the code we've written in Boot.dev up to this point has acted more like a command line tool: it runs, does its thing, and then exits.

Servers are different. They run forever, waiting for requests to come in, processing them, sending responses, and then waiting for the next request. If they didn't work this way, websites and apps would be down and unavailable _all the time_!

## Debugging a Server

Debugging a CLI app is simple:

1. Write some code.
2. Build and run the code.
3. See if it did what you expected.
4. If it didn't, add some logging or fix the code, and go back to step 2.

Debugging a server is a little different. The _simplest_ way (minimal tooling) is to:

1. Write some code.
2. Build and run the code.
3. _Send a request to the server using a browser or some other HTTP client._
4. See if it did what you expected.
5. If it didn't, add some logging or fix the code, and go back to step 2.

_Make sure you're testing your server by hitting endpoints in the browser before submitting your answers._

## Restarting a Server

I usually use a single command to build and run my servers, assuming I'm in my `main` package directory:

```bash
go run .
```

This builds the server and runs it in one command.

To stop the server, I use `ctrl+c`. This sends a signal to the server, telling it to stop. The server then exits.

To start it again, I just run the same command.

Alternatively, you can compile a binary and run it instead

```bash
go build -o out && ./out
```