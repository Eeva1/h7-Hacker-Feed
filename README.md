# h7-Hacker-Feed

## x) (disobey2023) Need for network visibility in the age of modern EDR - Ville Vainikka and Henri Aalt

## Valtori

- Finnish Government's ICT centre
- around 80 000 end users & 100 client organizations
- 1400 employees
- Valtori is responsible for the government's common environments security
- Client organizations get services from else where also

- Valtori has invested a lot for the IT security lately. They have about 100 employees working with security, when before it was about 50 security employees.
- They have outsourced and decentralized services, because no vendor has all the services
- They do a lot of market research
- Transition to cloud native tools as soon as they are ready to implement
- They have 18 diofferent Cyyber Security Services mixed from 50 different technology stacks
- They use EPP/EDR and SASE

- Endpoint protection normally comprise of visibility and controls
- Valtori is focusing on visibility for endpoints/end users in their presentation, but they say the principles apply to infra/services
- Visibilty enables investigations and threat hunt

- Valtori uses Microsoft Defender for EPP and EDR, but the brand is not important
- And they use SASE and SIEM

- EDR OS sees: API calls the program makes to use OS resources
    - memory
    - File
    - Network

- Network visibilty
    - EDR and SASE get basic IP, domain, port, device, user and OS info
    - EDR sees the starting process info, which 
    - EDR sees a TCP session, SASE sees it as multiple HTTP app level events
    - Next level firewall

## Case: Detecting (& preventing) C2's using network visibility 

- User is running Win 11 and is a normal user without admin rights
- There is no Applocker-policy in place
- MS Defender for end point running as EDR-solution
- User is tricked to download and run malware's or ransomware's from the Internet

- everything starts with phishing email which contains a link to site, which contains a link to download exe-file (dropper or fake client)
- then the fake client downloads the payload from the Internet (zip-file)
- extracts the payload and puts the exe-service to a users appdata, creates the link to the user's start up and then starts the service
- Then the fake client can communicate ovet the internet using GET-requests (HTTPS) to connect C2 server

- The presentator klicks the link, and downloads the exe-file and then they got the C2-connection
- and then the hacker can give demands to the victim machine
- and because there is not any policies to block Apps, the Defender for endpoint doesn't alarm either
- By using Power Shell you can run GET-commands and steal the files very sinmply

## Case 2

- They simulate the scenario where is the threat actor
- the presentator downloaded the different client App that communicates with the different address
- And we could see that the secure web gateway is not perfect. They could get the C2 connection working, because the domain was save and used in somewhere else. Then Domain has just offboarded and can be used again
- Then you can dowload the files using Power Shell commands
- The secure web gateway helped to prevent the set up but it was not perfect. 
- The point is not to show absolut control, but to detect and use e.q. threat hunt
- First thing is to detect C2-tunnels based on the high amount of the GET-requests (the presentators have done that before...)

  ![image](https://github.com/Eeva1/h7-Hacker-Feed/assets/149093822/a3827ab1-60ee-4147-92c3-69cf364050e4)

- And this is about X, Y and Z

![image](https://github.com/Eeva1/h7-Hacker-Feed/assets/149093822/ade69323-f0c1-4813-9d0a-3a60c1d7cc15)

- So nothing is definity, but just stuff you can use to do more and better threat hunting, and when you get a lot of different ways of finding that the certain domain is bad, then you propably have a case.
- Then it is better to go and check the other logs, like EDR logs 

## Summary of C2 detecton and prevention

- Do not let the user's run any Applications to the workstations
          - there will still be vulnerabilities and bypasses using LOLBINs, but it raises the bar and EDR's are very good for these techniques
- The network control and visibility are usually the last line of defense, if the attacker gets around the app controla and EDR

- APPLOCKER + NETWORK CONTROL & VISIBILITY + EDR + LOGS (from all of them) = MAXIMIZE PREVENTATION & DETECTION -capabilities

## Detecting AiTM (Adversary-in-the-middle)

- is detecting something what has already happened
- An attacker can get password and other user login, and session cookie that works without multi factor auhtentication

![image](https://github.com/Eeva1/h7-Hacker-Feed/assets/149093822/0003dc2c-58c2-4530-aebf-ff3f5a689eb5)
Aalto, H. Vainikka, V.

- When you get the IoC, the logs show how many users fell into the ruse and were compromised
- Then you can see all the logins, and how the whole sign in process went
- So it's clear that the account is compromised
- Decrypted initial HTTP URI followed the login process, and you know for who must force credential refresh

![image](https://github.com/Eeva1/h7-Hacker-Feed/assets/149093822/da8e1bdc-1913-4fb5-b3d4-264d474b038c)
Aalto, H. Vainikka, V.

## Summary

- If you can, get both.
- If you are forced to choose, pick EDR
- XDR (Extended detective and research)

Sources: 

Aalto H. & Vainikka V. 2023. Disobey 2023. Need for network visibility in the age of modern EDR - Ville Vainikka and Henri Aalto. YouTube video. URL: https://www.youtube.com/watch?v=lkaaodZ46o4. Accessed: 12.12.2023
