---
layout: post
toc: True
title: Unit 7 ArrayList P3
description: A Unit of documents that overview Array Lists in Java
authors: Drishya, Arnav, Tanuj, Jason
categories: ['AP CSA']
type: ccc
permalink: /csa/unit7-p3/unit7-5
menu: nav/CSA_Units/csa_unit7_p3.html
---

# 7.7:Ethical issues around data collection

- **Privacy Risks**: Personal data can be vulnerable to breaches or misuse when stored in systems. Programmers need to protect it.
  
- **Protection Methods**:
  - **Delete Data**: Remove personal info when it’s no longer needed.
  - **Minimize Data**: Only collect essential information.
  - **Anonymize Data**: Use methods like `hashCode()` in Java to hide real info.
  - **Encrypt**: Secure data so it can’t be easily accessed even if stolen.

The main goal? Keep personal data safe with smart coding practices.

# 7th mini Hack:
What can be used in place of the blank to ensure the users data is cleared?


```java
ArrayList<String> userData = new ArrayList<>();
userData.add("John Doe");
userData.add("john@example.com");

// Once you're done using the data
userData.clear(); // Removes all entries
userData = null;  // Sets the variableto null
```
