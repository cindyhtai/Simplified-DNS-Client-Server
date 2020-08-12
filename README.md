# Simplified-DNS-Client-Server
A simplified version of a DNS client and server using UDP sockets. 

###The client will perform the following functions:
1. Read in 3 arguments from the command line:
   - IP address of server (127.0.0.1)
   - Port of server (e.g. 9999)
   -Hostname (e.g. host1.student.test)
2. Send a request with the specified hostname to the server using the message format specified
3. Wait for a response using a 1 second timeout period.
   - If a response arrives within the timeout period, print out the server response as shown in
this document
   - If not, re-send the message (same sequence number) for a maximum of 3 attempts before
printing an applicable message and exiting

###The server will perform the following functions:
1. Read in 2 arguments from the command line:
   - IP address of server (127.0.0.1)
   - Port of server (e.g. 9999)
2. Read in the master file named “dns-master.txt” 
3. Store the resource records (type A) in data structures in main memory suitable for searching
4. Respond to requests from the DNS client for hostnames in the domain using the message format
specified
5. Return an error if the name queried does not exist in the domain.
6. The program should still work if the master file is modified to include different hostnames, or IP
addresses

###Simplifying Assumptions:
* Only one question in question section
* Only one answer in answer section (one IP address per host)
* Class is always of type Internet (IN)
* Only type A resource records

###Test Cases:
All DNS messages must adhere to the DNS Message Format specified in this document:
1. Look up existing name
2. Look up non-existent name
3. Look up name when server not running (On Windows, run the server but comment out responses)
