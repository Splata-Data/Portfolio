# Offensive Security Intro

**Author:** Kevin Curtis

---

## Introduction

This document describes the completion of an Offensive Security task, where a guided walkthrough was provided to scan a web URL for hidden directories and perform a simulated bank transfer.

---

## Task Overview

* **Objective:** Scan a web URL for hidden directories, navigate to one of these directories, and transfer $2000 USD from account `2276` to my account `8881`.
* **Tools Used:** Virtual Machine, Gobuster application, Terminal

---

## Execution Details

1. Upon launch, the Virtual Machine already had a web browser opened to the specified URL.
2. Tasked with launching a Terminal and using the command:
   ```bash
   gobuster -u http://fakebank.thm -w wordlist.txt dir
   ```

### Explanation of Command Components

* `gobuster`: Tool to execute.
* `-u`: Indicates the website to scan.
* `-w`: Specifies which `.txt` file will be used to search for hidden directories.
* `dir`: Indicates to search for directories.

---

## Gobuster Scan Results

The scan displayed two hidden directories:
* `/images` (Status: `301`)
* `/bank-transfer` (Status: `200`)

---

## Task Completion Steps

1. Navigated to the URL specified through scan result: `http://fakebank.thm/bank-transfer`
2. Input target accounts to transfer from (`2276`) and to (`8881`) along with the amount (`$2000`).
3. Redirected to the 'My Account' page, where a message displayed that the answer to the room was `BANK-HACKED`.

---

## Significance

Directory scanning is a crucial tactic for identifying potential vulnerabilities and hidden resources on a web server. These resources should be protected by passwords and firewall security as they could be exploited for malicious intent.

---

## Conclusion

Gobuster was executed for efficient directory scanning, and a simulated bank transfer was performed without issue. The room was completed successfully.