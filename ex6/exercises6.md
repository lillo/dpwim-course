# Web programming in Go

# Exercise 1

Write a Web application that works as a database to store clinical records.  A clinical record is an instance of the struct `PatientRecord`
```go
type PatientRecord struct {
    RecordID string
    PatientID string
    TestID string
}
```
The server stores records as JSON files following the example of the wiki we discussed during the lecture.
Design the application end-points allowing users to perform the various operations. 
The server should have a page to insert a new patient record, a page to see a patient record, and a way to retrieve the records of a given patient. 