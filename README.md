# Linux-Log-Analysis-Detecting-Suspicious-Web-Activity
This project, I used basic Linux commands to analyze a web server access log and identify suspicious activity in Ubuntu .The goal was to simulate a SOC analyst investigating potential malicious behavior. 🧠 Tools Used: Linux Terminal cat ls pwd grep wc.Steps Performed:
Navigated the system using:
Bash
pwd
ls
cd
Opened and reviewed the log file:
Bash
cat access.log
Identified repeated IP address:Bash
grep 3.18.18.132 access.log
Counted number of requests from that IP:
Bash
grep 3.18.18.132 access.log | wc -l
👉 Result: 53 requests from a single IPCounted failed requests (404 errors):
Bash/administrator
This indicates directory scanning / reconnaissance activity
Majority of responses were 404 (Not Found)
🛡️ Conclusion:
The activity observed suggests an automated scanning attempt to locate vulnerable admin panels. No successful access was detected, indicating the server was not vulnerable to these specific requests.
grep "404" access.log | wc -l
👉 Result: 214 failed requests
🚨 Findings:
A single IP address (3.18.18.132) made multiple requests to the server
The requests targeted:
/phpMyAdmin
/mysql administrator 
