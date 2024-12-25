# NotPetya Analysis Project

## Project Overview
This project focuses on the destructive ransomware "NotPetya," which caused significant disruption in June 2017. Through hands-on experimentation, the project examines its origins, mechanisms, and impact.


## Introduction
NotPetya is a ransomware that exploits vulnerabilities in Microsoft Windows systems. Unlike traditional ransomware, its main goal is to disrupt operations rather than collect ransom payments.

## Objectives
1. Analyze the propagation and encryption mechanisms of NotPetya.
2. Perform static analysis using IDA Pro.
3. Observe its impact in a controlled virtual environment.

## Configuration
- **Virtualization Platform:** VirtualBox
- **Operating System (VM):** Windows
- **Analysis Tools:**
  - IDA Pro
  - Process Monitor (ProcMon)
  - Process Hacker (ProcHacker)

## Methodology
### Virus Acquisition
The NotPetya malware sample was downloaded from the [GitHub repository](https://github.com/NTFS123/MalwareDatabase) maintained by NTFS123.

### Environment Setup
The virus was analyzed in a controlled virtual machine environment with tools such as ProcMon and ProcHacker.

### Execution
The file `notPetya.dll` was executed using the following command in an administrative prompt:
```bash
rundll32 notPetya.dll, #1
```
The `#1` represents the first entry point of the DLL file.

### Analysis
- **Infection Mechanism:** Exploits vulnerabilities like EternalBlue, EternalRomance, and EternalChampion.
- **Propagation:** Uses tools like PsExec and WMI for lateral movement.
- **Encryption:** Encrypts the Master Boot Record (MBR) and Master File Table (MFT) using AES-128 and RSA-2048 encryption.
- **Payload:** Overwrites the MBR, rendering systems unrecoverable.
- **Static Analysis:** Conducted using IDA Pro to identify key API calls and malicious routines.

## Screenshots
### Observations
- **ProcMon Output:** Displays process creation and shutdown commands.
- **Task Scheduler:** Shows scheduled malicious activities.
- **Ransom Screen:** Displays the ransom note demanding Bitcoin payment.
- **IDA Pro Analysis:** Highlights API calls such as `WNetAddConnection2W` and data destruction routines.

## Conclusion
The analysis revealed that NotPetya is a highly destructive ransomware designed to disrupt operations and cause irreversible damage. Its encryption methods and propagation techniques demonstrate sophisticated design. This project highlights the importance of secure environments for malware analysis and the need for robust cybersecurity measures.

## Disclaimer
This analysis was conducted in a secure, controlled environment for educational and research purposes only. Handling malware requires strict adherence to cybersecurity best practices.
# NotPetya-Ransomware
