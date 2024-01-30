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

3. Navigate to Azure search field and search and select "App Services"

<p align="center">
<br/>
<img src="https://i.imgur.com/LuhCcg6.png" height="80%" width="80%" alt="appservices"/>

<br />
<br />



4. Select "+ create" to start creation of Application

<p align="center">
 <br/>
<img src="https://i.imgur.com/ZkYUp8I.png" height="80%" width="80%" alt="SSH"/>

<br />
<br />




5. In the "Basics" tab select the following:

-Subscription/Resource Group: Select the Resource group that was created is Step 1.

-Name: Whichever name you create will be the name for the Web app I decided on "Davidcyberblog"

-Publish: Select "Code."

-Runtime Stack: Select "PHP 8.2"

-Operating System: Select "Linux."

-Region: Select the same region that was used for the resource group.

<br/>

<p align="center">
The following image shows the completed "Basics" tab: <br/>
<img src="https://i.imgur.com/tk6Y9il.png" height="80%" width="80%" alt="SSH"/>

<br />
<br />


6. Normally this step is where you would create your App Service Plan by:


-Under "Linux Plan," select "Create New" and then enter any name for your project plan

-Under "Sku and size," select "Change size."

-The spec picker will pop up on the right-hand side of your screen.
(This allows you to choose the pricing structure of your web app.)

-Select "Dev/Test" and "Plan B1" (the green option), and then click "Apply," 

(In my example I selected the completely free tier so I could not customize these options, the more you are willing to pay the more space and bandwidth will be allowed for your application)


<p align="center">
Example: <br/>
<img src="https://i.imgur.com/agGvXUv.png" height="80%" width="80%" alt="SSH"/>

<br />
<br />


7. You can leave all other options is other tabs as default. Select the "Review + Create" tab.


<p align="center">
<br/>
<img src="https://i.imgur.com/tk6Y9il.png" height="80%" width="80%" alt="SSH"/>

<br />
<br />

8. Select "Create" at the bottom
   
<p align="center">
<br/>
<img src="https://i.imgur.com/ydowDy9.png" height="80%" width="80%" alt="SSH"/>

<br />
<br />


9. Once App has been created and deployed you will be able to find it by clicking "Go to Resource" , or searching "App Services" in the Azure search field.
Application Page: <br/>
<img src="https://i.imgur.com/HHsWStq.png" height="80%" width="80%" alt="SSH"/>

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
