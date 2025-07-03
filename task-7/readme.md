# Task 7 - Identify and Remove Suspicious Browser Extensions
## Objective 
To understand the risks associated with browser extensions and learn how to identify, review, and remove potentially harmful or unnecessary ones to improve browser security and performance.

### Tools Used
- Browser: `Google Chrome`
- Extension Manager: `chrome://extensions/`
- Online Research: `Google`, `Reddit`, `Chrome Web Store Reviews`

### Steps Performed
> #### 1. Accessed Extension Manager

- Opened Google Chrome and navigated to chrome://extensions/
- Enabled "Developer Mode" to get more insights into each extension

> #### 2. Reviewed Installed Extensions

Inspected each extension based on the following criteria:

**Criteria**      **Checked For**
- Extension Name          - Generic, unknown, or misleading names
- Developer               - Unknown developer or missing publisher details
- Permissions             - "Read and change all data on websites", clipboard access, file access, etc.
- Reviews                 - Low star ratings, user complaints, mentions of malware
- Usage                   - Not being used or used only once in the past
- Behavior                - Injects ads, modifies search engine, causes browser slowness

> #### 3. Identified Suspicious Extensions

  Based on the above checks, the following extensions were identified as suspicious:

Suspicious Extension [***1: PDF Converter Pro***](https://chromewebstore.google.com/detail/word-to-pdf-converter-pro/ddbmednkcaaciannkbjaineoecjkclfg)

- Permissions: Access to all websites
- Developer: Unknown
- Reviews: Negative, mentions of browser hijacking
- Action: Removed
"Click the link below to view the evidence related to `*word to pdf converter*`: [evidence.md](https://github.com/0xV1RU/Elevate_lab_intern/blob/main/task-7/%F0%9F%93%81%20evidence.md)"

Suspicious Extension ***2: Search Manager***
- Permissions: Change default search engine, track browsing activity
- Behavior: Redirected searches, injected ads
- Action: Removed

Suspicious Extension ***3: Weather Tab***
- Permissions: Full access to tabs, browsing history
- Developer: Unverified
- Usage: Not required or used
- Action: Removed

***4. Removed Extensions***
- Used the `Remove` button from the *extension manager* for each suspicious extension and restarted Chrome.

***5. Verified Performance***
- Browser loading time improved
- No unwanted redirections or ads observed after cleanup

### How Malicious Extensions Can Harm Users
Malicious browser extensions can cause a variety of serious security and privacy issues, including:

- Stealing Personal Data

> *Extensions can read everything on web pages — passwords, credit cards, messages — especially when they have “read and change all data” permission.* 

- Injecting Ads or Malware

> *Some inject fake ads, popups, or malicious scripts into websites you visit. These might download malware or redirect you to phishing sites.*

 - Tracking & Surveillance

> *Malicious extensions often track every site you visit, creating a profile on you without your consent.*

-  Browser Hijacking

> *They may change your default homepage or search engine to a shady one, and redirect you to ad sites.*

- Background Spying

> *Even when inactive or disabled, some extensions run silently in the background, collecting data or waiting for a command from an attacker (backdoor behavior).*

- Keylogging or Form Spying

> *Some log whatever you type into forms — usernames, passwords, private chats.*

- Bypassing Browser Security

> *Advanced malicious extensions can disable browser security protections or inject JavaScript on trusted websites to exploit vulnerabilities.*



### Learning Outcomes

- Gained awareness of how browser extensions can compromise security.
- Learned to check permissions, reviews, and developer credibility.
- Realized the importance of keeping browser environments clean.
