# Project 8 - Pentesting Live Targets

Time spent: **7** hours spent in total

> Objective: Identify vulnerabilities in three different versions of the Globitek website: blue, green, and red.

The six possible exploits are:
* Username Enumeration
* Insecure Direct Object Reference (IDOR)
* SQL Injection (SQLi)
* Cross-Site Scripting (XSS)
* Cross-Site Request Forgery (CSRF)
* Session Hijacking/Fixation

Each version of the site has been given two of the six vulnerabilities. (In other words, all six of the exploits should be assignable to one of the sites.)

## Blue

Vulnerability #1: SQL Injection (SQLI)
GIF Walkthrough: <img src='https://github.com/santis25/codepath_wk08_s17/blob/master/gifs/codepath_websec_w08_obj03.gif' title='Video Walkthrough' width='' alt='Video Walkthrough' />
    Error in Detail: After trying the SQLI in all the user input forms, as well as the GET parameters I could find. I found the vulnerability occured in the Blue site, in the salesperson page. The 'id' GET parameter was not sanitized before being passed to the database query resulting in a delay of 5 seconds after passing in ' OR SLEEP(5)=0--' as the 'id' parameter.

Vulnerability #2: __________________


## Green

Vulnerability #1: Username Enumeration
GIF Walkthrough: <img src='https://github.com/santis25/codepath_wk08_s17/blob/master/gifs/codepath_websec_w08_obj01.gif' title='Video Walkthrough' width='' alt='Video Walkthrough' />
    Error in Detail: The error output is assigned a different class name depending on whether the username was found or not. If the username was found it will be assigned the class name "failure" which results in a bold font error message. If the the username was not found then it will be assigned the class name "failed" which results in regular unemphasized text. The css is different for these two classes.

Vulnerability #2: __________________


## Red

Vulnerability #1: Insecure Direct Object Reference (IDOR)
GIF Walkthrough: <img src='https://github.com/santis25/codepath_wk08_s17/blob/master/gifs/codepath_websec_w08_obj02.gif' title='Video Walkthrough' width='' alt='Video Walkthrough' />
    Error in Detail: The salesperson.php which takes a GET parameter 'id' to retrieve the salesperson information does not validate its requests. The other two sites do not retrieve the information of the tenth salesperson, they instead redirect to the territories page if they get an 'id' of a salesperson they are not permitted to show.

Vulnerability #2: __________________

Bonus Objective #1;
Obtained all database names globitek_red,globitek_blue,globitek_green, information_schema, mysql, sys etc. Obtained globitek databases tables information, and users table in more detail including id, username, and hashed_password fields. This was all done using sqlmap and attacking the SQL injection found in Objective 3 on the Blue site.

## Notes

The main challenge I faced was retrieving the admin password.



$2y$10$I.Jwfc8R3xaFwlAlPn5U3OLAQXrE0c2fakN8rR4j2TW0gRVMd6U6a
admin PASSWORD DEFAULT
$2y$10$XjIxjjn.vjHbuxsRsKYQLOk6R5CU0HcnB4vouxcAh7ehEMIeb4GoO
admin PASSWORD BCRYPT
$2y$10$ujt4w2BQnyR5Zc6bcxoyhOSNStjkeTkBaVTsH8ri508OxYcCEAi9O
