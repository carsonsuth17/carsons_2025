---
layout: post
title: Sprint 5 Blog
description: Blog for Database and Full Stack Feature
permalink: /datablog/
comments: true
---

## Intro

### Program Goals:
- Connect users with similar music tastes to build a community.
- Provide artist recommendations to enhance music discovery.
- Facilitate meaningful interactions through shared music interests.

**Insert image after complete:** Home Page

### Individual Feature:
- Develop a recommendation system based on user-inputted artist preferences.
- Help users discover new artists aligned with their music tastes.
- Enhance user engagement and satisfaction through tailored suggestions.

**Insert image after:** Feature

## List Requests

### Dictionary converted into JSON  
The static user data is stored in a **dictionary**, which is then converted into **JSON format** for easy API handling.

**Insert image after:** Dictionary to JSON

### Fetching JSON into DOM  
The frontend fetches JSON from the API and displays it dynamically in a table.

**Insert image after:** JSON to DOM

### Querying from Database  
SQLAlchemy is used to interact with the database, simplifying queries.

**Insert image after:** Query all records

#### Query Filtering  
- Querying by `UID` and fetching the **first matching record**.

**Insert image after:** Query by UID

### ArtInfoResource Class  
Methods handle **CRUD operations** on the database.

**Insert image after:** Create method  
**Insert image after:** Read method  
**Insert image after:** Update method  
**Insert image after:** Delete method  

## Algorithmic Code Request

### GET, POST, PUT, DELETE Methods  
The `ArtInfoResource` class provides full CRUD functionality.

**Insert image after:** Get and Post methods  
**Insert image after:** PUT method  
**Insert image after:** DELETE method  

### Sequencing, Selection, and Iteration  
- Data handling follows a structured flow using **GET** requests with JSON responses.

**Insert image after:** GET method with sequencing, selection, and iteration  

### Parameters and JSON Response  
- **Input:** `name`, `uid`, `favorite artist`  
- **Output:** JSON response with requested information or error message.

**Insert image after:** Parameters sent in JSON  

## Call to Algorithm Request

### Fetching Data from API  
Frontend makes a **POST request** to the API.

**Insert image after:** Post Request  

### Handling API Response  
- Normal condition response.

**Insert image after:** Post Response  

- Data is displayed in a **table format**.

**Insert image after:** Table  

### Error Handling  
- API returns **error responses** when invalid data is provided.

**Insert image after:** Error Response  
