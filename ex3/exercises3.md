# Networking programming in Go

## Exercise 1
Write a TCP server that listens on port 9999. When a client connects, the server
answers by sending today's date (see the package [`time`](https://pkg.go.dev/time)), and then it closes the
connection. Finally, write a TCP client to test your server.

## Exercise 2
Extend the previous exercise as follow.  When the client connects, it first
sends a message with a location name in the IANA Time Zone format (see [`time.LoadLocation`](https://pkg.go.dev/time@go1.21.3#LoadLocation)).  Then, the server answers by sending today's date in the requested time zone.
Finally, write a TCP client to test your server.

*Hint*: You may have a look [here](https://reintech.io/blog/an-introduction-to-gos-time-tzdata-package-time-zone-data) to deal with time zones.

## Exercise 3
Re-implement Exercise 2 using the UDP protocol.

## Exercise 4
Write a program that takes a URL of a web page as parameter, downloads the
requested page and extracts all URLs it links.

*Hint*: You may have a look at [this page](https://blog.logrocket.com/deep-dive-regular-expressions-golang/) and [this page](https://yourbasic.org/golang/regexp-cheat-sheet/) to learn about regular expressions in Go.

## Exercise 5
Write a TCP file server that listens for incoming connections on port 2018. The
server manages the directory `dbox` and allows clients to operate on files in
that directory.  In particular, the server can answer the following requests:

| Operation name | Description                                                              |
|----------------|--------------------------------------------------------------------------|
| `ls`           | return the list of files inside `dbox`                                   |
| `cat file`     | return the content of `file`                                             |
| `rm file`      | remove the `file` and return the result of the operation                 |
| `get file`     | download the `file` and save it in the current directory                 |
| `info file`    | return info about the file, e.g., its size, the last accessed date, etc. |


Test your server using the `telnet` or `nc` command line tools.