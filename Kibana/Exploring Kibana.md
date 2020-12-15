## Activity File: Exploring Kibana

* You are a DevOps professional and have set up monitoring for one of your web servers. You are collecting all sorts of web log data and it is your job to review the data regularly to make sure everything is running smoothly. 

* Today, you notice something strange in the logs and you want to take a closer look.

* Your task: Explore the web server logs to see if there's anything unusual. Specifically, you will:

:warning: **Heads Up**: These sample logs are specific to the time you view them. As such, your answers will be different from the answers provided in the solution file. 

---

### Instructions

1. Add the sample web log data to Kibana.

2. Answer the following questions:

    - In the last 7 days, how many unique visitors were located in India?
	244

    - In the last 24 hours, of the visitors from China, how many were using Mac OSX?
	71
	

    - In the last 2 days, what percentage of visitors received 404 errors? How about 503 errors?
	10  and  19

    - In the last 7 days, what country produced the majority of the traffic on the website?
	Chinda
	
    - Of the traffic that's coming from that country, what time of day had the highest amount of activity?
	Around Noon
	
    - List all the types of downloaded files that have been identified for the last 7 days, along with a short description of each file type (use Google if you aren't sure about a particular file type).
	gz : gzip file compression
	css: website display data
	zip: zip file compression/decompression
	deb: debian installation filetype for an application
	rpm: redhat linux installation filetype for an application
	

3. Now that you have a feel for the data, Let's dive a bit deeper. Look at the chart that shows Unique Visitors Vs. Average Bytes.
     - Locate the time frame in the last 7 days with the most amount of bytes (activity).
	Dec 6, 2020
     - In your own words, is there anything that seems potentially strange about this activity?
	Only one visitor created a large amount of traffic for that visit.
	

4. Filter the data by this event.
     - What is the timestamp for this event?
	Dec 6, 2020 @ 18:00
     - What kind of file was downloaded?
	RPM
     - From what country did this activity originate?
	India
     - What HTTP response codes were encountered by this visitor?
	200

5. Switch to the Kibana Discover page to see more details about this activity.
	
     - What is the source IP address of this activity?
	35.143.166.159
     - What are the geo coordinates of this activity?
	lat 43.34121 lon -73.6103075
     - What OS was the source machine running?
	windows 8
     - What is the full URL that was accessed?
	artifacts.elastic.co/beats/metricbeat/metricbeat-6.3.2-i686.rpm
	
	
     - From what website did the visitor's traffic originate?
	http://facebook.com/success/jay-c-buckey

6. Finish your investigation with a short overview of your insights. 

     - What do you think the user was doing?
	attempting to download the metricbeat RPM
     - Was the file they downloaded malicious? If not, what is the file used for?
	I don't believe so. 
     - Is there anything that seems suspicious about this activity?
	possibly I'm unsure
	
     - Is any of the traffic you inspected potentially outside of compliance guidlines?
	It seemed like they were accessing the data from a suspicious source: facebook

---
© 2020 Trilogy Education Services, a 2U, Inc. brand. All Rights Reserved.  
