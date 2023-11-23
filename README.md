# Phishing-Prevention
The following was is the Phishing Prevention room in the Try Hack Me Soc 1 path.  



Phishing Case 1
Scenario: You are a Level 1 SOC Analyst. Several suspicious emails have been forwarded to you from other coworkers. You must obtain details from each email for your team to implement the appropriate rules to prevent colleagues from receiving additional spam/phishing emails. 

Task: Use the tools discussed throughout this room (or use your own resources) to help you analyze each email header and email body.

What brand was this email tailored to impersonate?

I am using Google Admin Toolbox Messageheader to examine the header of the email.

![image](https://github.com/Rory33160/Phishing-Prevention/assets/47018034/a92b99e9-361d-42ba-aedc-5eb227cd75e6)

Answer:

Netflix

What is the From email address?

![image](https://github.com/Rory33160/Phishing-Prevention/assets/47018034/20d26270-5b8a-4d3a-8e1b-5e79b554937a)

What is the originating IP? Defang the IP address. 
The originating ip address also found in the header 

![image](https://github.com/Rory33160/Phishing-Prevention/assets/47018034/ad54f624-d069-4128-bda6-87fc11345565)

Or
![image](https://github.com/Rory33160/Phishing-Prevention/assets/47018034/ce54c6a1-15c6-444b-87ee-ee02b85af234)

Cyberchef provide the defang answer.
209[.]85[.]167[.]226

From what you can gather, what do you think will be a domain of interest? Defang the domain.

This is found in the header of the email

![image](https://github.com/Rory33160/Phishing-Prevention/assets/47018034/4cb9f65f-b6eb-492f-b153-432166bc851c)



The Cyberchef defanged answer is 

![image](https://github.com/Rory33160/Phishing-Prevention/assets/47018034/8506192e-f661-40e8-a135-115316805c95)

What is the shortened URL? Defang the URL.

Phishing Case 2

Scenario: You are a Level 1 SOC Analyst. Several suspicious emails have been forwarded to you from other coworkers. You must obtain details from each email for your team to implement the appropriate rules to prevent colleagues from receiving additional spam/phishing emails. 

A malicious attachment from a phishing email inspected in the previous Phishing Room was uploaded to Any Run for analysis. 

Task: Investigate the analysis and answer the questions below.

What does AnyRun classify this email as?
AnyRun classify the email as 


![image](https://github.com/Rory33160/Phishing-Prevention/assets/47018034/ae339bdf-4433-439f-b8d3-1f9a45a8eb1c)

Suspicious Activity 

What is the name of the PDF file?
Payment-updateid.pdf

What is the SHA 256 hash for the PDF file?

![image](https://github.com/Rory33160/Phishing-Prevention/assets/47018034/b7d4a8bd-275f-4b9b-9830-f567dec7ac78)

SHA 256: cc6f1a04b10bcb168aeec8d870b97bd7c20fc161e8310b5bce1af8ed420e2c24

What two IP addresses are classified as malicious? Defang the IP addresses. (answer: IP_ADDR,IP_ADDR)
An easier way to get this to click  “Text report”.


![image](https://github.com/Rory33160/Phishing-Prevention/assets/47018034/25353710-0f04-43b2-aa0a-a601235370bf)

Scroll to connections 

![image](https://github.com/Rory33160/Phishing-Prevention/assets/47018034/75727b7f-ceb3-4e24-846e-6fd09d37a0de)


By clicking “NEXT” in the connections category we can find the second malicious ip address.

From there we can defang the addresses in Cyberchef 

![image](https://github.com/Rory33160/Phishing-Prevention/assets/47018034/80d0fc86-138b-4f87-a7f1-6be9bbbd8bed)


The answer according to requested format is 2[.]16[.]107[.]24,2[.]16[.]107[.]83


What Windows process was flagged as Potentially Bad Traffic?
In the same Text Report under process we can find the Windows process.

![image](https://github.com/Rory33160/Phishing-Prevention/assets/47018034/3987cb58-a3ac-4c10-a1fc-89567c620ac7)

svchost.exe

Phishing Case 3
What is this analysis classified as?
[The screenshot answers the first 3 questions]
Text Report 

![image](https://github.com/Rory33160/Phishing-Prevention/assets/47018034/5a612985-8145-4709-b378-c7a26d80cd46)

Malicious activity

What is the name of the Excel file?
CBJ200620039539.xlsx

What is the SHA 256 hash for the file?
5F94A66E0CE78D17AFC2DD27FC17B44B3FFC13AC5F42D3AD6A5DCFB36715F3EB

What domains are listed as malicious? Defang the URLs & submit answers in alphabetical order. (answer: URL1,URL2,URL3)

The text report under DNS or domain will give us the three malicious domains.


![image](https://github.com/Rory33160/Phishing-Prevention/assets/47018034/0f476dbc-3f01-4e7e-b7c3-e078ae4e4896)

We can then question ask us to defang and sort alphabetically.
The recipe we use is defang url and sort [alphabetically]


![image](https://github.com/Rory33160/Phishing-Prevention/assets/47018034/d4205d8a-f61d-4116-9fd7-ef8d5bebea64)


What IP addresses are listed as malicious? Defang the IP addresses & submit answers from lowest to highest. (answer: IP1,IP2,IP3)
The IP addresses are under connections and DNS requests in the text report.

![image](https://github.com/Rory33160/Phishing-Prevention/assets/47018034/f2faa8b7-f439-41bb-88c7-149d12da852c)

Then we defang and sort in Cyberchef.

![image](https://github.com/Rory33160/Phishing-Prevention/assets/47018034/256232ab-3f81-441f-815c-8d661554cc06)

204[.]11[.]56[.]48,75[.]2[.]11[.]242,103[.]224[.]182[.]251


What vulnerability does this malicious attachment attempt to exploit?


![image](https://github.com/Rory33160/Phishing-Prevention/assets/47018034/fb1f685b-d79b-41c4-8e34-5a313ad5a2d2)



CVE-2017-11882


Phishing Email 4 - SMTP Status Codes

What Wireshark filter can you use to narrow down the packet output using SMTP status codes?
smtp.response.code

What Wireshark filter can you use to narrow down the packet output using SMTP status codes?
We’re using Wireshark to find the code by searching with smtp.response.code == 220


![image](https://github.com/Rory33160/Phishing-Prevention/assets/47018034/8284860a-836c-432b-afd4-274db2a3c3c2)

The answer being <domain> Service ready

One packet shows a response that an email was blocked using spamhaus.org. What were the packet number and status code? (no spaces in your answer)

I am using the display filter in Wireshark with the string “spamhaus.org” 

![image](https://github.com/Rory33160/Phishing-Prevention/assets/47018034/6b20cfd8-b04c-4cd2-920a-b5974f3b43cc)

Here we can see the packet number is 156 and the code is 553

Based on the packet from the previous question, what was the message regarding the mailbox?

![image](https://github.com/Rory33160/Phishing-Prevention/assets/47018034/cf7cbcf5-631b-4d11-b3d3-b0374c893fdc)

mailbox name not allowed

What is the status code that will typically precede a SMTP DATA command?

Base on the hint provided for this question [the server is now waiting for the “body” of the message],
we can deduce that the status code is 354

![image](https://github.com/Rory33160/Phishing-Prevention/assets/47018034/9d013055-608f-4f73-9cd8-957f40d86286)

SMTP Traffic Analysis


What port is the SMTP traffic using?
From networking we know it is port 25, or to see it in Wireshark

![image](https://github.com/Rory33160/Phishing-Prevention/assets/47018034/a2e1675c-54e7-40ad-ae25-7136eac393e7)

How many packets are specifically SMTP?
By searching for smtp we see the at the bottom right 512.


![image](https://github.com/Rory33160/Phishing-Prevention/assets/47018034/6ad298b3-d5fb-42ac-abca-85b709e0ede5)

What is the source IP address for all the SMTP traffic?
Wireshark.org gives us a clue where to start with this search


![image](https://github.com/Rory33160/Phishing-Prevention/assets/47018034/072278ba-7872-4523-aa32-a437987857f5)

We are using im.address
 
![image](https://github.com/Rory33160/Phishing-Prevention/assets/47018034/95762d43-cf23-4ca4-8530-b77e1e66aa16)


This returns the result of

10.12.19.101

What is the filename of the third file attachment?

![image](https://github.com/Rory33160/Phishing-Prevention/assets/47018034/a7d9e3b0-cca0-4d44-8097-83af7db0ecfa)


Searching for SMTP with the string search of “filename” located the third file attachment.
Attachment.scr

How about the last file attachment?

Using the same search criteria as above and cycling through to the last attachment, we can see that the answer is 
.zip





















































































