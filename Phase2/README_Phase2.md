
# ICS344 Project – Phase 2: SIEM Dashboard Analysis

## 📁 Phase Overview

In this phase, we analyzed the attack executed in Phase 1 using a SIEM platform (Splunk) by uploading and visualizing logs from both the attacker (Kali Linux) and the victim (Metasploitable3). Our focus was on identifying SSH login patterns and evaluating the attacker’s behavior via log analysis.



## 👥 Group Information

- **Group Number:** 8
- **Members:**
  - Mohammad Alamri : 202165790
  - Saeed Almullais : 202034400
  - Meshal Almutairi : 202169150


## 📊 Splunk Search Queries Used

```spl
-----------------------------
index=main host="metasploitable3-ub1404"
-----------------------------
index=main host="attacker"
-----------------------------
index=main "Accepted password" OR "Login Successful"
-----------------------------
index=main host="attacker" OR host="metasploitable3-ub1404" | timechart count by host
-----------------------------
index=main "Accepted password" OR "Failed password"
| rex "for (?<username>\w+) from"
| top username
-----------------------------
```


## 📸 Screenshots Summary

| Screenshot                    | Description                                 |
|-------------------------------|---------------------------------------------|
| `victim_raw_logs.png`         | SSH logins to victim (accepted + failed)    |
| `attacker_raw_logs.png`       | Metasploit login success + exploit logs     |
| `successful_logins_combined.png` | Combined view of successful logins       |
| `attack_timeline_chart.png`   | Timeline chart showing event flow by host   |
| `user_login_attempts_chart.png` | Most frequently targeted usernames        |


## ✅ Outcome

We were able to:
- Visualize the SSH brute-force behavior
- Distinguish attacker vs victim logs
- Track login attempts and outcomes over time
- Extract usernames targeted during the attack