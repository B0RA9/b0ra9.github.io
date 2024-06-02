---
title: Web Investigation
layout: post
categories: [CyberDefenders, Network]
tags: [pcap,Wireshark,easy]     # TAG names should always be lowercase
---

<h1><span style="color:Green"> <em>Web Investigation </em> </span></h1>

***Scenario:***

Ansive online bookstore renowned for its vast selection of literature. BookWorld prides itself on providing a seamless and secure shopping experience for book enthusiasts around the globe. Recently, you've been tasked with reinforcing the company's cybersecurity posture, monitoring network traffic, and ensuring that the digital environment remains safe from threats.

Late one evening, an automated alert is triggered by an unusual spike in database queries and server resource usage, indicating potential malicious activity. This anomaly raises concerns about the integrity of BookWorld's customer data and internal systems, prompting an immediate and thorough investigation.

As the lead analyst on this case, you are required to analyze the network traffic to uncover the nature of the suspicious activity. Your objectives include identifying the attack vector, assessing the scope of any potential data breach, and determining if the attacker gained further access to BookWorld's internal systems.

answer the questions, los geht’s :

<h3><span style="color:Red">Q1: By knowing the attacker's IP, we can analyze all logs and actions related to that IP and determine the extent of the attack, the duration of the attack, and the techniques used. Can you provide the attacker's IP?</span></h3>

Opening the file with wireshark, one of the first things I start with, is the **`Statistics**` Tab :

Taking a look at the `Protocol Hierarchy` and the `Conversations` we can get a first insight of what’s going on.

From there we can see that most of the traffic was `HTTP` with **"Address A": "111.224.250.131" → "Address B": "73.124.22.98"** being the most interesting conversation. Filtering by this conversation or HTTP , we can see that **111.224.250.131** is conducting some sort of fuzzing on **73.124.22.98. with gobuster.**

<h3><span style="color:Green">Answer 1: 111.224.250.131</span></h3>

<h3><span style="color:Red">Q2: If the geographical origin of an IP address is known to be from a region that has no business or expected traffic with our network, this can be an indicator of a targeted attack. Can you determine the origin city of the attacker?</span></h3>

Using any online tool like [https://ipinfo.io](https://ipinfo.io/) we get the city.

<h3><span style="color:Green">Answer 2: Shijiazhuang</span></h3>

<h3><span style="color:Red">Q3: Identifying the exploited script allows security teams to understand exactly which vulnerability was used in the attack. This knowledge is critical for finding the appropriate patch or workaround to close the security gap and prevent future exploitation. Can you provide the vulnerable script name?</span></h3>

After a quick look at the packets we can use different filters to get the script name like this one, given that gobuster is a recon tool, and the attacker will eventually visit any found pages with a  browser (or another tool).

**`(!(http.user_agent == "gobuster/3.6")) && !(http.response.code == 404) && http`**

From there we can see that `search.php` is the vulnerable script, and an SQL attack is performed.

<h3><span style="color:Green">Answer 3 : serach.php</span></h3>

<h3><span style="color:Red">Q4: Establishing the timeline of an attack, starting from the initial exploitation attempt, What's the complete request URI of the first SQLi attempt by the attacker?</span></h3>

Keeping the same filter, we can easily identify the request `357`  as the first SQLi attempt.

<h3><span style="color:Green">Answer 4 : /search.php?search=book%20and%201=1;%20--%20-</span></h3>

<h3><span style="color:Red">Q5 : Can you provide the complete request URI that was used to read the web server available databases?</span></h3>

We can use this filter to clean the packets a little bit :

`(((!(http.user_agent == "gobuster/3.6")) && !(http.response.code == 404) && http) && !(frame.len == 425)) && !(http.response.code == 500)`

then we can look for any presence of `INFORMATION_SCHEMA` or similar request used to retrieve the database schema, the request number `1520` is what we need.

<h3><span style="color:Green">Answer 5: /search.php?search=book%27%20UNION%20ALL%20SELECT%20NULL%2CCONCAT%280x7178766271%2CJSON_ARRAYAGG%28CONCAT_WS%280x7a76676a636b%2Cschema_name%29%29%2C0x7176706a71%29%20FROM%20INFORMATION_SCHEMA.SCHEMATA--%20-</span></h3>

<h3><span style="color:Red">Q6 : Assessing the impact of the breach and data access is crucial, including the potential harm to the organization's reputation. What's the table name containing the website users data?</span></h3>

Just after a couple of requests, the request number `1553` is the response with the table names.

<h3><span style="color:Green">Answer 6 : customers</span></h3>

<h3><span style="color:Red">Q7:  The website directories hidden from the public could serve as an unauthorized access point or contain sensitive functionalities not intended for public access. Can you provide name of the directory discovered by the attacker?</span></h3>

Assuming that a redirection will occur when a dir is requested without “/” at the end, we can use this filter:

`(!(http.user_agent == "gobuster/3.6")) && (http.response.code ==301 ) && http`

and we got the dir name.

<h3><span style="color:Green">Answer 7: /admin/</span></h3>

<h3><span style="color:Red">Q8: Knowing which credentials were used allows us to determine the extent of account compromise. What's the credentials used by the attacker for logging in?</span></h3>

Using the same filter as Q5, we can see that in the request `1589` the attacker tried to extract the username and password of the admin user and get the creds in the request `1591.`

Also filtering by `http.request.method==POST` we can see the attacker got access with those credentials in the `tcp stream 695` .

<h3><span style="color:Green">Answer 8 : admin:admin123!</span></h3>

<h3><span style="color:Red">Q9: We need to determine if the attacker gained further access or control on our web server. What's the name of the malicious script uploaded by the attacker?</span></h3>

We can filter by POST method to quickly find the answer:

`http.request.method==POST`

<h3><span style="color:Green">Answer 9 : NVri2vhp.php</span></h3>
