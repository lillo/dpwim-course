# Networking and Web programming in Go

# Exercise 1

Write a TCP server that listens on port 8888 and works as a database to store
clinical records.  A clinical record is an instance of the struct `PatientRecord`
```go
type PatientRecord struct {
    RecordID string
    PatientID string
    TestID string
}
```
The client and the server communicates by exchanging JSON messages.
You have to design the format of the request and response messages but the following constraints must be taken into account. 
A client can send two kinds of messages:
 1) the client sends an instance of `PatientRecord`: the server stores the new
    record in the database and answers by sending the answer with a status `OK` and the message "OK stored!";
 2) the client sends `patientId`: the server computes the number `n` of records it stores for that patient and answer by sending the string "Records: `n`".

Finally, write a client to test your server.

# Exercise 2

Rewrite the Exercise 1 as a Web application following the example we discussed during the lecture.
Design the application end-points allowing users to perform the various operations. 
The server should have a page to insert a new patient record, a page to see a patient record, 
and a way to retrieve the records of a given patient. For simplicity, you can store the patient records
on files. 