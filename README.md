# Phirautee
A proof of concept crypto virus to spread user awareness about attacks and implications of ransomwares. Phirautee is written purely using PowerShell and does not require any third-party libraries. This tool steals the information, holds an organisation’s data to hostage for payments or permanently encrypts/deletes the organisation data. 

Phirautee is a Living off the Land (LotL) ransomware which means it utilises legit powershell commands and operations to work against the operating system. 

![image](https://user-images.githubusercontent.com/3501170/79039950-3c465600-7c28-11ea-9390-df6594573abb.png)

# Legal Disclaimer
This project must not be used for illegal purposes or for hacking into system where you do not have permission, it is strictly for educational purposes and for people to experiment with.
<B><I>
 - Performing any hack attempts or tests without written permission from the owner of the computer system is illegal.
 - If you recently suffered a breach or targeted by a ransomware and found techniques or tools illustrated in this presentation similar, this neither incriminates my involvement in any way, nor implies any connection between myself and the attackers.
- The tools and techniques remain universal and penetration testers and security consultants often uses them during engagements. 
</I></B>

# DEF CON 28 Safe Mode

Over the past few years, ransomware has gone wild and organisations around the world are getting targeted leading to the damage and disruption. As we all know that the threat landscape is changing rapidly and we hear the fuss about ransomware infection at the offices or read about it in the news. Have you ever wondered how threat actors are writing ransomwares? What level of sophistication and understanding is required to target an organisation? In this demo, we will utilise the native Windows commands to build ransomware and target a host via phishing. Introducing Phirautee, a proof of concept crypto virus to spread user awareness about attacks and implications of ransomwares. Phirautee is written purely using PowerShell and does not require any third-party libraries. This tool steals the information, holds an organisation's data to hostage for payments or permanently encrypts/deletes the organisation data. The tool uses public-key cryptography to encrypt the data on the disk. Before encrypting, it exfiltrates the files from the network to the attacker. Once the files are encrypted and exfiltrated, the original files are permanently deleted from the host and then tool demands a ransom. The ransom is asked using the cryptocurrency for payments, so transactions are more difficult for law enforcement to trace. During the demonstration of Phirautee, you will see a complete attack chain i.e. from receiving ransomware attack via a phishing email and how the files get encrypted on the compromised systems. A detailed walkthrough of the source code would be provided to understand how hackers utilise simple methods to create something dangerous. I will end the demo with several defence mechanisms by performing forensics analysis on Phirautee using publicly available tools.

# Steps for setting up Data Exfilteration using Google Drive

Google offers a REST API that can be accessed via PowerShell to perform operations on the files such as upload, download and delete. The REST API allows you to leverage Google Drive storage from within your app.

![image](https://user-images.githubusercontent.com/3501170/89538185-986b6080-d83d-11ea-870d-fbc0df6b6f24.png)

Please follow below steps to perform exfilteration via phirautee ransomware.

Step 1: Visit https://console.cloud.google.com/cloud-resource-manager

Step 2: Click on "CREATE PROJECT"

![image](https://user-images.githubusercontent.com/3501170/89416241-4b6d8880-d770-11ea-91a2-cd3c621b1286.png)

Step 3: Once the project is created enable the Google Drive API by click on the "ENABLE APIS AND SERVICES".

![image](https://user-images.githubusercontent.com/3501170/89416365-81ab0800-d770-11ea-83aa-89ce6aff2de1.png)

Step 4: Locate the Google Drive related APIs in the AOI Library:

![image](https://user-images.githubusercontent.com/3501170/89417187-b075ae00-d771-11ea-9fb0-b501ec39364c.png)

Step 5: Once located enable the API. This would allow access to various operations via Google Drive.

![image](https://user-images.githubusercontent.com/3501170/89716879-15403b00-d9f4-11ea-8d9a-76f1db90746c.png)

Step 6: After enabling the API access click on the "create credentials" button.

![image](https://user-images.githubusercontent.com/3501170/89716900-4caee780-d9f4-11ea-9f09-6d1e6cbe0083.png)

Step 6: Now create OAuth Client ID Credentials

![image](https://user-images.githubusercontent.com/3501170/89716918-7e27b300-d9f4-11ea-816d-71b2b9d8a97d.png)

Step 7: Select Web Application as product type and configure the authorized redirect URI to https://developers.google.com/oauthplayground
![image](https://user-images.githubusercontent.com/3501170/89716949-b7602300-d9f4-11ea-9958-d3341917d1d4.png)

Step 8: Save your client ID and Secret. If you dont this can always be accessed from credentials in APIs & Services. Now browse to https://developers.google.com/oauthplayground

Step 9: Click on the gear icon and tick on the "Use your own OAuth credentials"
![image](https://user-images.githubusercontent.com/3501170/89716974-1c1b7d80-d9f5-11ea-84ad-85d5d567ebb1.png)

Step 10: Authorize the https://www.googleapis.com/auth/drive API and then Click “Exchange authorization code for tokens”. This should give you 200 OK in the response. Make sure you save your refresh access token. We will need this in the Phirautee to upload large files to the throwaway Google account. <br>

![image](https://user-images.githubusercontent.com/3501170/89717034-d7441680-d9f5-11ea-84e7-dfbb87bceda6.png)

![image](https://user-images.githubusercontent.com/3501170/89717044-f478e500-d9f5-11ea-804a-87d00471e686.png)

# Contribution & License

MIT License

Copyright (c) 2020 Viral Maniar

Permission is hereby granted, free of charge, to any person obtaining a copy
of this software and associated documentation files (the "Software"), to deal
in the Software without restriction, including without limitation the rights
to use, copy, modify, merge, publish, distribute, sublicense, and/or sell
copies of the Software, and to permit persons to whom the Software is
furnished to do so, subject to the following conditions:

The above copyright notice and this permission notice shall be included in all
copies or substantial portions of the Software.

THE SOFTWARE IS PROVIDED "AS IS", WITHOUT WARRANTY OF ANY KIND, EXPRESS OR
IMPLIED, INCLUDING BUT NOT LIMITED TO THE WARRANTIES OF MERCHANTABILITY,
FITNESS FOR A PARTICULAR PURPOSE AND NONINFRINGEMENT. IN NO EVENT SHALL THE
AUTHORS OR COPYRIGHT HOLDERS BE LIABLE FOR ANY CLAIM, DAMAGES OR OTHER
LIABILITY, WHETHER IN AN ACTION OF CONTRACT, TORT OR OTHERWISE, ARISING FROM,
OUT OF OR IN CONNECTION WITH THE SOFTWARE OR THE USE OR OTHER DEALINGS IN THE
SOFTWARE.

Any suggestions or ideas for this tool are welcome - just tweet me on [@ManiarViral](https://twitter.com/maniarviral)
