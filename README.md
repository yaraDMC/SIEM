# 🔥 SIEM with Splunk for Cyberattack Detection

## 🎯 Objective
Real-time security monitoring system capable of detecting:
- ✅ Brute force attacks
- ✅ Malware and ransomware
- ✅ Phishing attempts
- ✅ Web traffic anomalies

With Splunk correctly installed, we will run it.

![](https://github.com/yaraDMC/SIEM/blob/main/splunkinicio.png)


 We will upload sample data (attack logs) and download sample logs
as we will use Apache logs simulating attacks:
Create a folder and download the logs.

![](https://github.com/yaraDMC/SIEM/blob/main/descargalogs.png)


and upload the logs to Splunk
![](https://github.com/yaraDMC/SIEM/blob/main/subirlogs.png)

I used this one. 


"wget https://github.com/logpai/loghub/raw/master/Apache/Apache_2k.log"


We have already uploaded the logs and now we have them.
![](https://github.com/yaraDMC/SIEM/blob/main/logsee.png)

Some SPL

Searches for Threat Detection
-Brute Force Detection (SSH)
SPL Query:

index=main sourcetype=access_combined status=401 | stats count by src_ip | where count > 5

-Panel 1: Brute Force Attempts (Bar Chart)

splunkindex=security_logs "Failed login attempt" 
| timechart span=1h count by src_ip 
| head 10


