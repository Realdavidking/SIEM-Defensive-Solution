# SIEM-Defensive-Solution

<p align="center">
<br/>
<img src="https://imgur.com/QaKqeg0.png" height="80%" width="80%" alt="Splunk"/>

<br />
<br />
<h2>Description</h2>
This Project will demonstrate the steps on how to analyze log information from a fictious company's (Virtual Space Industry) Windows & Apache servers utilizing a SIEM (Splunk Enterprise). VSI has heard a rumor that a competitor may launch attacks to disrupt VSI's business. After I analyze past logs, I'll use my analysis to establish a baseline for user activity, create relavent alerts, reports and dashboards in order to notify VSI's SOC team of abnormal user activity which could be an indicator of a malicious actor.

<h2>Languages and Utilities Used</h2>

- <b>Linux</b>
- <b>Splunk Enterprise</b>
- <b>Splunk Processing Language</b>

<h2>Environments Used </h2>

- <b>Vagrant Virtual Machine</b>
- <b>Windows 10</b>

<h2>Project Guide:</h2>  

1. Initally I started a splunk container that was on my Virtual Machine and signed into Splunk Enterprise online.

2. In order to create a baseline for "regular" user activity it is necessary to upload log into Splunk after sigining in.

How to Upload log data:
- Select the option “Or get data in with the following methods.”
- Select "Upload"
- Click "Select File" and navigate to wherever you have log file saved on system.

<p align="center">
Selecting Log File: <br/>
<img src="https://i.imgur.com/PihyKiI.png" height="80%" width="80%" alt="Log Upload"/>

<br />

- You'll get brought to the "Set Source" page, change any configurations as necessary then select "Next"
- In the "Host" field value on the "Input Settings" page update the value to the log file's name and select "Review"
- Verify your chosen settings and select "Submit" to upload data.
- Click "Start Searching" and log data will populate. Organized in different fields (Time frame of data can be selected for analysis of events in a specific time period).

3. After I uploaded the Windows server log, I proceeded to analyze the information. The main fields i was interested in were: "Signature_id", "Signature", "User", "Status" and "Severity"

4. Next step was to design reports for those fields.

To Create Reports you just have to click on the relevant data field and select an appropriate Visualization for the data you are viewing, and then click the "Save As" option to save report specific to the data field.

<p align="center">
Report showing total count by Signature:<br/>
<img src="https://i.imgur.com/zk5ghI6.png" height="80%" width="80%" alt="totalcountsig"/>

<br />
<p align="center">
Report showing Severity:<br/>
<img src="https://i.imgur.com/4kSnNTw.png" height="80%" width="80%" alt="severity"/>

<br />
<p align="center">
Report Comparing Success and Failure of Windows Activity:<br/>
<img src="https://i.imgur.com/Ldj6vyX.png" height="80%" width="80%" alt="compare"/>

<br />

5. In order to create alerts for abnormal activity we need to make baseline of normal activity.

Using information from my reports I was able to determine an average baseline and threshold for hourly level of failed Windows activity, for the hourly count of the signature "an account was successfully logged on.", and for the hourly count of the signature "a user account was deleted".

To find the baseline I took the total amount of events for each data field and divided by the 24 hour range observed on the Windows server logs. To create an alert threshold for abnormal event activity I doubled this value.

6. How To create alert after establishing baseline & threshold:
   - On results page select "Save As" at the top right
   - Create a title and Description, then set permissions, alert type(scheduled or real time) and frequency.
   - Select the trigger condition and frequency for specific alert
(Ex: for each alert I selected "number of results" and set the value to anything greater than double the average baseline value, and had alert sent to the SOC team of VSI)

<br />
<p align="center">
Alert creation:<br/>
<img src="https://i.imgur.com/UebLKbh.png" height="80%" width="80%" alt="alertcreation"/>

<br />
<p align="center">
Alert for excessive failed login activity:<br/>
<img src="https://i.imgur.com/8F7PodM.png" height="80%" width="80%" alt="failedlogin"/>

<br />
<p align="center">
Alert for excessive login successful activity:<br/>
<img src="https://i.imgur.com/LSCjRQR.png" height="80%" width="80%" alt="successfullogin"/>

<br />
<p align="center">
Alert for excessive deleted User Accounts:<br/>
<img src="https://i.imgur.com/Zm7FwB7.png" height="80%" width="80%" alt="deleteduser"/>

<br />

7. Next I wanted to create a dashboard of visualizations that would be able to easily display data found in the in the Windows sever log. Dashboards are a great demonstrative tool to show others relavent info. After navigating back to the original search field, I proceeded to make visualizations of the previous mentioned data fields.
<br />
<p align="center">
Visualization displaying the different "signature" field values over time:<br/>
<img src="https://i.imgur.com/ZklVwB1.png" height="80%" width="80%" alt="signature"/>

<br />

8. After creating visualization Click "Save AS" and then "New Dashboard". You'll be able to name and save dashboard. To add more graphs to the dashboard, navigate back to search field, select relavent data field and create visualization and then save each to the newly created dashboard.

<br />
<p align="center">
Dashboard showing created Visualizations:<br/>
<img src="https://i.imgur.com/m0Wrg4s.png" height="80%" width="80%" alt="dashboard1"/>

<br />
<p align="center">
Dashboard showing created Visualizations:<br/>
<img src="https://i.imgur.com/0nCwysV.png" height="80%" width="80%" alt="dashboard2"/>

<br />

9. Next I navigated back to the Splunk Enterprise home page to set a new source, however this time I loaded VSI's Apache logs. And proceeded to analyze the data fields "method", "referer_domain", "status", "clientip", and "useragent". <br />

10. This analysis helped me create reports, discover basline "normal" activity, create alerts, design visualizations and build a dashboard showing the Apache server data.

<br />
<p align="center">
Visualization showing HTTP Requests by Method:<br/>
<img src="https://i.imgur.com/H62hNmn.png" height="80%" width="80%" alt="requestbymethod"/>

<br />

<p align="center">
Visualization showing Top 10 Domains:<br/>
<img src="https://i.imgur.com/BcPTV6E.png" height="80%" width="80%" alt="topdomains"/>

<br />
<p align="center">
Dashboard showing created Visualizations:<br/>
<img src="https://i.imgur.com/idNmZWY.png" height="80%" width="80%" alt="dashboard3"/>

<br />
<p align="center">
Dashboard showing created Visualizations:<br/>
<img src="https://i.imgur.com/UnksBbL.png" height="80%" width="80%" alt="dashboard4"/>

<br />
<br />


<!--
 ```diff
- text in red
+ text in green
! text in orange
# text in gray
@@ text in purple (and bold)@@
```
--!>
