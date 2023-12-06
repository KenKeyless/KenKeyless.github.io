---
layout: default
title: HTB Web Proxies Skill Assessment
---

## Setting Up BurpSuite

**Configuration for BurpSuite:**
- Open BurpSuite and set up your browser to proxy through it. Enable intercept to capture and manipulate web traffic.

![Image 4]( {{ site.baseurl }}/assets/images/2023-12-1-Web-Proxies-Skill_Assessment_images/images/image4.png)

## Navigating to /lucky.php

**Developer Tools for Page Access:**
- Access "/lucky.php" and activate the button in your browser's developer tools interface.

## Intercepting the Request

**Using BurpSuite for Request Intercept:**
- Click the enabled button to intercept the request in BurpSuite. Ensure the intercepted request reflects "getflag=true".

![Image 1]( {{ site.baseurl }}/assets/images/2023-12-1-Web-Proxies-Skill_Assessment_images/images/image1.png)

## Utilizing Repeater

**Sending Requests through Repeater:**
- Send the intercepted request to the Repeater tool in BurpSuite. Begin sending it repeatedly.

## Exploring Vulnerabilities

**Understanding Race Conditions:**
- Observe server response or button behavior; the flag may appear after sending requests multiple times, indicating a race condition or state change behavior.

**Persistence for Success:**
- Continue sending the request through Repeater until the flag appears. Persistence and experimentation help identify timing or state-based vulnerabilities.

---

### Decoding the Encoded Cookie

The `/admin.php` page uses a multiple-encoded cookie. Decode the cookie until you obtain a value with 31 characters, then submit it as the answer.

**Request Interception for Decoding:**
- Access "/admin.php" and intercept the login request to retrieve the encoded cookie.

**Decoding Process:**
- Initially encoded in hexadecimal, the cookie reveals a 64-character Base64 encoded string upon decoding. Try fuzzing the last character of the decoded md5 cookie using alphanumeric characters.

---

### Capturing Metasploit Request

While using 'auxiliary/scanner/http/coldfusion_locale_traversal' in Metasploit, capture the request to manually verify and repeat. Identify the 'XXXXX' directory called in '/XXXXX/administrator/..'.

**Metasploit Setup for Request Capture:**
- Configure Metasploit to use BurpSuite as a proxy to capture requests during the attack.

**Intercepting Requests with Burp Suite:**
- Burp Suite intercepts requests made by Metasploit, allowing inspection and verification.

---

### Mitigation Strategies

- **Cookie Expiration:**
  - Set appropriate expiration times for cookies to minimize vulnerability windows.

- **Session Management:**
  - Employ secure session management practices to prevent session fixation attacks.
