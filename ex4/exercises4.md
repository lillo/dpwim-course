# Data serialization and network programming in Go

## Exercise 1
Consider the `todo` app we discuss in class. Extend it by implementing a new `Render` that outputs the list of todos in [CSV](https://pkg.go.dev/encoding/csv) format.
Finally, update the `-list` flag of the application to allow the user to specify the desired output format — either table or csv.

## Exercise 2
The [Go Object Binary (gob) serialization mechanism](https://pkg.go.dev/encoding/gob) is a built-in feature that allows encoding and decoding of Go data structures into a compact binary format. It is used to serialize (encode) Go objects, such as structs, arrays, maps, and other data types, into a byte stream that can be stored, transmitted over a network, or saved to a file. Later, these objects can be deserialized (decoded) back into their original form.

Extend the `todo` app we discuss in class by implementing a new `Storage` that allows loading and saving the list of todos in a file using the `gob` format.

## Exercise 3
Environment variables are key-value pairs used to store configuration settings and information that can be accessed by applications and processes. 
They provide a way to configure the behavior of software without modifying the code directly. Environment variables typically store data such as system paths, user information, API keys, and other configuration details. 
The functions [`os.Getenv`](https://pkg.go.dev/os@latest#Getenv) and [`os.LookupEnv`](https://pkg.go.dev/os@latest#LookupEnv) retrieves the value of the environment variable by name.

Environment variable values can be set directly in the shell, passed to a program via the shell, or loaded from a file, typically with the .env extension.
The library [`godotenv`](https://github.com/joho/godotenv) can be used to load environment variables from a file.

Extend your solution to [Exercise 2](#exercise-2) by allowing the user to specify the file in which to store the todo list via an environment variable. 
If the file has a `.json` extension, use the JSON `Storage`; if it has a `.gob` extension, use the GOB `Storage`.

## Exercise 4
Write a TCP server that listens on port 9999. When a client connects, the server
answers by sending today's date (see the package [`time`](https://pkg.go.dev/time)), and then it closes the
connection. Finally, write a TCP client to test your server.

## Exercise 5
Extend the previous exercise as follow.  When the client connects, it first
sends a message with a location name in the IANA Time Zone format (see [`time.LoadLocation`](https://pkg.go.dev/time@go1.21.3#LoadLocation)).  Then, the server answers by sending today's date in the requested time zone.
Finally, write a TCP client to test your server.

*Hint*: You may have a look [here](https://reintech.io/blog/an-introduction-to-gos-time-tzdata-package-time-zone-data) to deal with time zones.

## Exercise 6
Re-implement [Exercise 5](#exercise-5) using the UDP protocol.
