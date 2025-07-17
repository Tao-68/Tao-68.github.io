---
title: "TryHackMe: Monday Monitor"
author: Kleiner
categories: [TryHackMe]
tags: [windows, Wazuh, Sysmon]
render_with_liquid: false
media_subpath: /images/thm_monday_monitor/
image:
  path: room_icon.png
---

[![Tryhackme Room Link](monday_monitor_img.png){: width="600" height="300" .shadow}](https://tryhackme.com/room/mondaymonitor){: .center }

## Scenario

Swiftspend Finance, the coolest fintech company in town, is on a mission to level up its cyber security game to keep those digital adversaries at bay and ensure their customers stay safe and sound.

Led by the tech-savvy Senior Security Engineer John Sterling, Swiftspend's latest project is about beefing up their endpoint monitoring using Wazuh and Sysmon. They've been running some tests to see how well their cyber guardians can sniff out trouble. And guess what? You're the cyber sleuth they've called in to crack the code!

The tests were run on Apr 29, 2024, between 12:00:00 and 20:00:00. As you dive into the logs, you'll look for any suspicious process shenanigans or weird network connections, you name it! Your mission? Unravel the mysteries within the logs and dish out some epic insights to fine-tune Swiftspend's defences.

Once logged in, navigate to the **Security** events module and use the saved query **`Monday_Monitor`** to access the logs.

## Approach

We head over to the dashboard and view the data present to us. Press the **Floppy Disk** icon to apply the **`Monday_Monitor`** filter. We also need to set the timeline to **Apr 29, 2024, between 12:00:00 and 20:00:00**. 

We filter out the following attributes as columns in the table:  **data.win.eventdata.commandLine, eventdata.parentCommandLine** because these attributes provide critical insights into the exact commands executed by a process and its parent. This helps trace the origin and propagation of potentially malicious activity, such as identifying the initial vector (e.g., a downloaded file execution) and understanding the chain of process creation that led to system compromise.

Note: The questions for this task are not answered in order as the solutions were found by going through logs and noticing the anomalies within those logs along the way. 

### 


#### Question 1: Initial access was established using a downloaded file. What is the file name saved on the host?

#### Question 2: What is the full command run to create a scheduled task?

#### Question 3: What time is the scheduled task meant to run?

#### Question 4: What was encoded?

#### Question 5: What password was set for the new user account?

#### Question 6: What is the name of the .exe that was used to dump credentials?

#### Question 7: Data was exfiltrated from the host. What was the flag that was part of the data?
