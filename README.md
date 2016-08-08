# SuperSQL
Automating SQL Injection in a list of URLs or Request Files

Prerequisites:

  1. Kali Linux
  2. Sqlmap installed

Description:

We often miss out testing of various URLs for SQL Injection. We may be specifically testing few URLs and come to a decision whether an application is vulnerable to SQL Injection or not. However, this is very dangerous and we may be missing a pramater of a URL.

This script helps in automating list of URLs or request files. It has two modes:

  1. When we are manually testing other vulnerabilities in an application using Burp or any other proxy tool, we keep browsing the application and all requests get captured in HTML request history. Manually testing all these URLs with all parameters is not feasible. Once all testing is complete, we can simply copy all the URLs (For BurpSuite, CTRL+A in "HTML History") and paste them in a file. We can then run the script. This will test all the GET requests.
  2. While browsing if we see some important requests (GET, POST or other methods) simply copy the request in a file. Keep copying all suspicious requests in separate files and keep all of them in a folder. Now run the script. This will test all other methos including GET, POST, etc.

Instructions to run the script:

1. Go to the folder where the script has been copied.

2. Run the below command:

chmod +x supersql

3. Execute the script:

./supersql

When prompted for choice

select '1' for testing GET URLs (where URLs have been copied in a file) and provide the file name with path

select '2' for testing all request files and provide the path of the directory where all the request files have been copied

Output will be in the format <date>/output_details/output

'output' file will be "@" separated file. Open it in excel and select separator as "@"

This file will include following details:

File / URL, Affected Parameter, Injection Type, Title, Payload

Also, affected request files will be copied in <date>/output_details/.
