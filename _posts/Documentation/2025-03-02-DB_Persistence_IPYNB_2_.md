---
layout: post
title: DB Persistence Writeup
description: DB Persistence Writeup
type: collab
toc: True
permalink: documentation/db_persist
comments: True
author: Eric Yu
categories: ['Collaboration']
---

# 📌 Database Persistence in Spring Backend

## 📝 Overview
This document provides an in-depth look at the **database persistence** feature implemented in the Spring backend. It covers its **significance**, **key concepts**, **schema design**, and **important functions** that facilitate data storage and retrieval.

---

## 1. Significance of the Feature
Database persistence is crucial for ensuring that application data is **stored reliably** and can be **retrieved when needed**. This feature:

✅ Enables **long-term** data storage.  
✅ Ensures **data integrity and consistency**.  
✅ Supports **efficient querying** and data manipulation.  
✅ Provides **scalability** and **maintainability** in a structured manner.  

Imagine if our SQLite database on the AWS suddenly gets wiped, how can we prevent all the database's info from being wiped? This is where Database Persistence comes in. 

---

## 2. Background Information

### 📌 2.1 What is Database Persistence?
Database persistence refers to the mechanism of **storing and managing data beyond the runtime** of an application. In a **Spring application**, persistence is typically handled using:

- **JPA (Java Persistence API)** – Abstraction for ORM frameworks.  
- **Hibernate** – Popular ORM framework for mapping Java objects to database tables.

### 🏛 2.2 Understanding Database Schema
A **database schema** defines the structure of the data, including **tables, relationships, and constraints**. In a Spring application, schemas are often defined using:

- **JPA Annotations** (`@Entity`, `@Table`, etc.)  
- **Database Migration Tools** (Liquibase/Flyway)  

If you have worked with the backend, you are sure to have seen this before, schema is defined in blocks of code that look like this:



```Java
@Entity
@Table(name = "users")
public class User {
    @Id
    @GeneratedValue(strategy = GenerationType.IDENTITY)
    private Long id;

    @Column(nullable = false, unique = true)
    private String username;

    @Column(nullable = false)
    private String password;

    @OneToMany(mappedBy = "user", cascade = CascadeType.ALL)
    private List<Order> orders;
    
    // Getters and Setters
}
```

As you can see, columns, whether they are nullable or not, whether they need to be unique, are all considered **schema**.

---

## 3. Flowcharts of the process

### 🛠 Importing process
![Image](https://github.com/user-attachments/assets/d3056c0b-1f86-4a8d-ad2d-bc2df30e727d)

### 🛠 Exporting process
![Image](https://github.com/user-attachments/assets/64e68016-0719-4f2a-9eab-00e518b09bac)
