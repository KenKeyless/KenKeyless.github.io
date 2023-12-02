---
layout: default
title: HTB Web Proxies Skill Assessmnent
---
1. **Setting Up BurpSuite:**
   - Open BurpSuite and configure your browser to proxy through it. Ensure the intercept is enabled to capture and manipulate web traffic.
<img class="project-image" src="{{site.baseurl}}/assets/images/2023-12-1-Web-Proxies-Skill_Assessmnent_images/images/image1.png" alt="Image 1">

2. **Navigate to /lucky.php:**
   - Access the "/lucky.php" page and open the developer tools in your browser. Enable the button within the developer tools interface.

3. **Intercept the Request:**
   - Click the enabled button and intercept the request using BurpSuite. The intercepted request should reflect "getflag=true".

4. **Send to Repeater:**
   - Transfer this intercepted request to the Repeater tool in BurpSuite. Begin sending the request repeatedly.

5. **Exploring Race Conditions:**
   - The server might exhibit a Race Condition or State Change behavior, where the flag only appears after sending the request multiple times. Observe any changes in the server's response or behavior of the button during this process.

6. **Persistence Pays Off:**
   - Keep sending the request through the Repeater tool until the flag eventually appears. This persistence and experimentation are crucial in identifying vulnerabilities reliant on timing or state changes.

---

The /admin.php page uses a cookie that has been encoded multiple times. Try to decode the cookie until you get a value with 31-characters. Submit the value as the answer.

1. **Intercept the Request:**
   - Access the "/admin.php" page and intercept the login request to acquire the encoded cookie.

2. **Decode the Cookie:**
   - Upon inspecting the cookie, it seems to be initially encoded in hexadecimal format. However, decoding this reveals another 64-character string, indicating a closer alignment with Base64 encoding.

3. **Fuzzing the Last Character:**
   - Try all alpha-numeric characters to fuzz the last character of the decoded md5 cookie. Encode each request with the identified encoding methods. Utilize the "alphanum-case.txt" wordlist from Seclist for the payload.

---

You are using the 'auxiliary/scanner/http/coldfusion_locale_traversal' tool within Metasploit, but it is not working properly for you. You decide to capture the request sent by Metasploit so you can manually verify it and repeat it. Once you capture the request, what is the 'XXXXX' directory being called in '/XXXXX/administrator/..'?

1. **Using Metasploit for Request Capture with BurpSuite:**
   - Open the Metasploit Framework console.
   - Search for the 'coldfusion_locale_traversal' module using the `search` command.
   - Set the required options: target IP (`RHOST`), target port (`RPORT`), and configure proxies to direct traffic through Burp Suite (`Proxies`).
   - Initiate the attack by executing the module with the `exploit` or `run` command.

2. **Intercept Requests with Burp Suite:**
   - As the attack runs, the requests will be routed through your defined proxy settings (`HTTP:127.0.0.1:8080`). Burp Suite will intercept the requests, allowing inspection.

---

**Mitigation Strategies:**
- **Limited Cookie Lifespan:**
  - Set appropriate expiration times for cookies to reduce the window of vulnerability.

- **Session Management:**
  - Employ secure session management practices to prevent session fixation attacks.
