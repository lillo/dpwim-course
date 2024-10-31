# Network programming in Go

## Exercise 1
Write a program that takes a URL of a web page as parameter, downloads the
requested page and extracts all URLs it links.

*Hint*: You may have a look at [this page](https://blog.logrocket.com/deep-dive-regular-expressions-golang/) and [this page](https://yourbasic.org/golang/regexp-cheat-sheet/) to learn about regular expressions in Go.

## Exercise 2
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

## Exercise 3
Consider the `chat` app discussed during the class. Reimplement it using the UDP protocol instead of TCP.
 