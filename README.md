# OSINT (Open Source Intelligence)

**Overview:** In this lab, open-source intelligence gathering techniques were applied to gather public information on networks and organizations.

**Skills Developed:** Google hacking, Shodan analysis, OSINT techniques to gather public data for reconnaissance.

**Tools Used:** Google, Shodan, Maltego, Recon-ng, TheHarvester, Spiderfoot

---

**Lab Details**

Introduction
Open Source Intelligence is the collection and analysis of information gathered from free data sources. This is mainly from free search engines can range from social media to radio, television, pictures and even patterns of movement. Overall to sum up Open Source Intelligence, it is any information an individual can find that isn’t paid for. This is also the first stage of an attack where the cyber criminal gathers as much information possible on the target using open source intelligence. This is called the Reconnaissance phase. In this lab, the usefulness of Open Source Intelligence will be explained and why the importance of gathering as much information possible before an attack is necessary. 
Objective
The objective of this week’s lab is to familiarize the user with Open Source Intelligence and information gathering techniques for the Reconnaissance phase of an attack on a target:
•	Google Hacking
•	Shodan
•	Recon-ng
•	The Harvester
•	Spiderfoot
•	Analysis questions

Results and Analysis
To begin this lab, the user will start by finding three different file types on Utica.edu using different Google hacking techniques. Google is a search engine that can be utilized to find specific information when used properly. First the user will search Utica.edu for three file types. If the user knows the url or website the user wishes to search and the types of files within the website the individual is searching for. Typing into the Google search bar ‘allinurl: Utica.edu filetype: pdf’ this will load all the pdf files within the url Utica.edu. In the figure below is a form for medical eave of absence for students. 
Figure 1: pdf document 

![image](https://github.com/user-attachments/assets/60b1b65a-d3a6-42c4-9576-817fab59127d)


The next filetype found under the Utica.edu site was a powerpoint slideshow. This looks to show how to create and update a login for the Pioneer Place at Utica College. This could help an individual understand the concepts of how the logins and passwords are created if the individual wanted to create malware or attempt a phishing attack. The search ‘link: Utica.edu filetype: ppt’ was used to find this presentation. The figure below shows the start of the slide. 
Figure 2: powerpoint document
 
![image](https://github.com/user-attachments/assets/e27324b5-ca4e-40d1-b5e5-a5ccd8f2af63)



Next searching for other documents but changing the search again to ‘index: Utica.edu filetype: jpg’ the search displayed a list of photos of students and the mascot from what looks to be 2015 due to a picture displaying homecoming 2015. One picture even included a student identification card. This could help any individual create another student card with their picture and name on it to gain access to the campus for more social engineering opportunities. Below is the image of the student ID card. For privacy reasons the name and part of the face has been blurred out. 
Figure 3: jpg document 

![image](https://github.com/user-attachments/assets/ebb05ae8-f4e1-4bf3-90eb-7329fdb86d42)


The next task for the user is to find a login page in the Utica.edu website that was unknown to the individual. Using google.com and searching ‘allinsite: Utica.edu “login”’. The second login for the results of the search is the login that is unknown to the user. Below in the figure is a screenshot of the login. Attempting to login allowed access but showed no results.


Figure 4: Unknown Login 

![image](https://github.com/user-attachments/assets/9eab22d3-e362-42ce-8b4d-54682b3d9118)


The next task was to find a web camera and Identify the IP address. Then using the IP address look up the physical location of the camera. The web camera found was a web camera over looking Armory Square in Syracuse, NY. Using google, the search was ‘webcam Syracuse NY’ due to starting off broad and not using any google hacks. Therefore, it wasn’t too specific and displayed negative results. The figure below displays what the webcam shows. 
Figure 5: webcam display

 ![image](https://github.com/user-attachments/assets/c6daee8d-0da1-438b-8d38-d0303001dda9)


When attempting to search the IP address of the camera using dig the results of the IP address were 104.21.54.71. However, after running whois through both IP address. The whois tool stated the ip address was located at 101 Townsend Street San Francisco CA. This could be due to a proxy server or VPN in use for the camera. Since at the top of the page it states the cross roads of the downtown Syracuse and personally I have been to the area. 
Figure 6: webcam IP information
 
![image](https://github.com/user-attachments/assets/dfe6752b-7576-45e6-8622-9564e9d8d4ea)


Using shodan.io to explore Utica.edu and the servers below, with the software versions, and what the name of each server could be. The table below from left to right will correlate the IP address to the software version to the perceived user. 
IP addresses	Software versions	Perceived users
72.237.4.41	TLSv1, TLSv1.1, TLSv1.2	Bannerweb1.utica.edu
72.237.4.72	TLSv1, TLSv1.1, TLSv1.2	Student Opinionnaire on Teaching
72.237.4.114	TLSv1, TLSv1.1, TLSv1.2	Off campus Login
72.237.4.216	TLS.v1.2, TLSv1.3	WSO2 Management Console
72.237.4.113	TLSv1.2, TLSv1.3	ECCI; Economic Crime and Cybersecurity Institute

Now using the IP addresses from above, the user will enter the IP addresses and locate the servers geographically using shodan.io search engine. It should be noted that servers with multiple results may have locations move when the page refreshes. Although, these can be for privacy concerns the server is possibly in the general area but at an undisclosed location. 
72.237.4.41
 ![image](https://github.com/user-attachments/assets/92f55989-a0c6-49ef-899f-d1ccc11818c3)

72.237.4.72 
![image](https://github.com/user-attachments/assets/c42ef132-a76a-4ece-be67-e30826a957bb)

72.237.4.114 
![image](https://github.com/user-attachments/assets/96b20f01-5ac0-4344-939f-918c215bf756)

72.237.4.216 
![image](https://github.com/user-attachments/assets/e787d99b-d812-4566-a334-b5e209b49e0f)

72.237.4.113
![image](https://github.com/user-attachments/assets/a4999f81-a8a9-4086-8411-9e10b21a1712)

 
When searching for vulnerabilities on each host. The IP address, 72.237.4.72 for the Student Opinionnaire on Teaching has not been updated since 2012 and has 133 vulnerabilities. The vulnerabilities are listed as follows: "CVE-2016-2183, CVE-2014-0118, CVE-2016-2182, CVE-2017-9798, CVE-2016-2178, CVE-2016-2179, CVE-2015-3185, CVE-2015-3184, CVE-2015-3183, CVE-2022-28330, CVE-2016-2177, CVE-2013-6450, CVE-2016-6303, CVE-2016-6302, CVE-2016-6306, CVE-2016-6304, CVE-2015-3195, CVE-2017-7679, CVE-2013-6438, CVE-2020-1927, "CVE-2016-0703", "CVE-2016-0702", "CVE-2016-2181", "CVE-2016-2180", "CVE-2015-3196", "CVE-2015-3197", "CVE-2021-4044", "CVE-2016-8612", "CVE-2021-44790", "CVE-2014-0198", "CVE-2016-2109", "CVE-2016-2108", "CVE-2016-2105", "CVE-2016-2107", "CVE-2016-2106", "CVE-2014-0195", "CVE-2020-13938", "CVE-2020-35452", "CVE-2022-22719", "CVE-2020-1934", "CVE-2021-34798", "CVE-2016-4975", "CVE-2019-0217", "CVE-2014-3523", "CVE-2013-5704", "CVE-2016-2176", "CVE-2022-31813", "CVE-2014-5139", "CVE-2015-0287", "CVE-2014-0221", "CVE-2015-0286", "CVE-2013-2249", "CVE-2010-5298", "CVE-2014-0231", "CVE-2021-26690", "CVE-2021-26691", "CVE-2014-3511","CVE-2019-0220", "CVE-2014-8275", "CVE-2016-0798", "CVE-2016-0799", "CVE-2016-0797", "CVE-2021-39275", "CVE-2014-3581", "CVE-2015-3194", "CVE-2022-29404", "CVE-2018-1312", "CVE-2019-10092", "CVE-2014-3505", "CVE-2014-3506", "CVE-2014-3507", "CVE-2014-0224", "CVE-2014-0226", "CVE-2014-3508", "CVE-2014-3509", "CVE-2022-22721", "CVE-2022-22720", "CVE-2017-15710", "CVE-2017-15715", "CVE-2019-10098", "CVE-2015-0228", "CVE-2016-5387", "CVE-2021-40438", "CVE-2022-23943", "CVE-2018-17199", "CVE-2014-0160", "CVE-2015-0209", "CVE-2018-1301", "CVE-2018-1302", "CVE-2018-1303", "CVE-2014-3470", "CVE-2015-0205", "CVE-2015-0204", "CVE-2020-11985", "CVE-2015-0206", "CVE-2014-3571", "CVE-2014-3570", "CVE-2014-3572", "CVE-2016-0800", "CVE-2013-4353", "CVE-2022-26377", "CVE-2014-0098", "CVE-2014-3513", "CVE-2016-8743", "CVE-2014-3512", "CVE-2015-0289", "CVE-2015-0288", "CVE-2016-7056", "CVE-2014-3510", "CVE-2015-1789", "CVE-2015-1788", "CVE-2014-8176", "CVE-2013-1896", "CVE-2014-3566", "CVE-2014-3567", "CVE-2017-3735", "CVE-2014-3568", "CVE-2016-2842", "CVE-2015-0292", "CVE-2015-0293", "CVE-2017-9788", "CVE-2014-8109", "CVE-2015-1790", "CVE-2015-1791", "CVE-2015-1792", "CVE-2015-4000", "CVE-2013-6449", "CVE-2022-30556", "CVE-2018-1283", "CVE-2017-3167", "CVE-2016-0705", "CVE-2022-28615", "CVE-2022-28614", "CVE-2016-0704". 
For the IP address, 72.237.4.113, the ECCI; Economic Crime and Cybersecurity Institute there were 33 vulnerabilities found. The vulnerabilities are listed as follows: "CVE-2022-31628", "CVE-2022-31629", "CVE-2022-0778", "CVE-2020-1934", "CVE-2021-34798", "CVE-2022-29404", "CVE-2022-22721", "CVE-2022-28330", "CVE-2020-11993", "CVE-2021-44224", "CVE-2021-33193", "CVE-2022-22720", "CVE-2019-17567", "CVE-2022-31813", "CVE-2021-40438", "CVE-2021-36160", "CVE-2022-28614", "CVE-2022-23943", "CVE-2020-1927", "CVE-2022-31630", "CVE-2020-9490", "CVE-2020-11984", "CVE-2021-44790", "CVE-2021-26690", "CVE-2021-26691", "CVE-2022-26377", "CVE-2022-30556", "CVE-2020-13938", "CVE-2020-13950", "CVE-2022-22719", "CVE-2022-28615", "CVE-2020-35452", "CVE-2021-39275". There were no other vulnerabilities found for the other host IP addresses. 

When using Recon-ng, the user must first install the repository by using the ‘sudo apt-get install recon-ng’ command. Then the user must install all modules by executing the ‘marketplace install all’ command. If other errors appear its allowed to happen. Once the Recon-ng command line appears the user will load the module for the google search by running the ‘modules load recon/doamins-hosts/google_site_web’ command. This will load the google website module in recon-ng. Then the user will want to go to allow unset the options by executing ‘options unset SOURCE’ to change the source options. Then type in ‘options set source Utica.edu’. This will have Recon-ng use Utica.edu as the source for the google module. Then type run and hit enter and Recon-ng will find as much information as possible. Although no IP addresses were found it shows how powerful the tool is and the ways the tool can be utilized to find information. The results are in the screenshots below. 
 
 ![image](https://github.com/user-attachments/assets/823fe09b-ef6c-4c52-90d1-7b874fffd71a)
 
  ![image](https://github.com/user-attachments/assets/c517ea43-d80f-4f5f-a2a5-f1821cbc168b)

![image](https://github.com/user-attachments/assets/df744d5a-5600-4111-9069-f0c5ab1feecf)

![image](https://github.com/user-attachments/assets/7a69df07-bfb2-4f15-8d18-73afc93cf495)


 
The next tool is the Harvester, by entering the command the Harvester -d Utica.edu -b google. The tool utilized google and found emails, and anything associated with Utica.edu. Although, there was also no IP addresses found. The screenshot below shows the results from the tool. 

![image](https://github.com/user-attachments/assets/3afabc02-49b7-4636-8f6c-475d935a98fd)

 
The next tool is called Spiderfoot, to run the tool the user must install the tool on Kali Linux the same was the previous tools were installed. When using Spiderfoot the user will need to know the ip address of the machine the individual is using. If the user is using the virtual machine, it is most likely that it is 127.0.0.1 and the port number needed is 5000. The command needed to use the Graphical User Interface for Spiderfoot is ‘Spiderfoot -l 127.0.0.1:5000’. When the command is entered a message will appear. The user will click on the link in the message that will take them to the Spiderfoot website to allow the user to scan the IP address of their choice. Below is what the output of the command would look like. 
 

![image](https://github.com/user-attachments/assets/555983b0-f064-47f4-bb15-20f34920a4df)





When the user runs the scan in the website, if the user chooses to have Spiderfoot find all options about the target it can take some time due to Spiderfoot finding every possible outcome about the ip address. When using the Utica.edu ip address 72.237.4.113, due to this being what appeared after a dig search in Linux. The following were the results from a Footprint Spiderfoot scan. Although, the results needed to be cancelled due to time. 
 

![image](https://github.com/user-attachments/assets/c2bd05a6-3ec4-4fc1-b4c6-9a9184458ada)




Analysis
The results are similar and different from Shodan, Recon-ng and Spiderfoot. Shodan showed where servers were located geographically and the IP addresses where the others did not. Recon-ng could show surmounts of data when it came to looking for any type of information regarding Utica.edu. It also allowed the user to search for other information regarding Utica College that could be stored in a file for later. This can be very useful for an attacker. Recon-ng also had other built in modules not only for domains and host but other ways to gather information as well. Spiderfoot is a great way to gather information, although, its better to make sure the All search is not chosen. Due to the searching of the website just takes too long to make a report. If the scan for specific information regarding the IP be malicious or how much information is in the information or allow the target to know a search is being inquired. Spiderfoot is a great way to search due to all the information that can be inquired. There is no one tool that is the best. It’s the combination of all these tools put together that makes an individual skillful in gathering information and knowledgeable about the system that needs protecting. Unless the individual is attempting in committing a breach which starts with the use of these tools. No one tool will ever be used by an individual it will be the combination of multiple tools. 
