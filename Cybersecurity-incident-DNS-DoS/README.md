# Incident Report: Network Traffic Analysis (Suspected DNS DoS)

## Project Overview
This project involves a security analysis of network traffic logs following a service disruption. As part of a cybersecurity incident response simulation, `tcpdump` logs were analyzed to determine why users were unable to access a client website, identifying a critical failure in DNS resolution.

## Scenario Details
*   **Target Website:** www.yummyrecipesforme.com
*   **Reported Symptom:** Users experienced long page load times followed by a "destination port unreachable" error.
*   **Analysis Tool:** `tcpdump`

### Network Log Evidence (tcpdump) Image:
<img width="1561" height="771" alt="Event log" src="https://github.com/user-attachments/assets/29842592-da5a-47bb-92ae-239c3fe57cc0" />
