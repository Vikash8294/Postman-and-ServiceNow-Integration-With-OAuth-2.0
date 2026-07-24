# 🚀 ServiceNow And Postman integration Using Import Set API and OAuth 2.0

Secure REST API Integration between **Postman** and **ServiceNow** using
**OAuth 2.0 Authorization Code Flow** and **Import Set API**.

------------------------------------------------------------------------

## 🎥 Demo Video

> After uploading your demo video to GitHub, replace the link below.

https://github.com/user-attachments/assets/

------------------------------------------------------------------------

# 📌 Project Overview

This project demonstrates how to securely create **Incident** records in
ServiceNow using **OAuth 2.0 Authentication** and the **Import Set
API**.

Instead of inserting records directly into the **Incident** table, the
data is first stored in an **Import Set Table** (staging table) and then
transformed into the Incident table using a **Transform Map**.

This approach is secure, scalable, and follows ServiceNow best
practices.

------------------------------------------------------------------------

# 📖 What is Integration?

Integration is the process of connecting two or more systems so that
they can communicate and exchange data with each other.

------------------------------------------------------------------------

# 📖 What is Postman?

Postman is an API testing tool that helps us send HTTP requests such as
**GET, POST, PUT, PATCH, and DELETE** and verify the API responses.

------------------------------------------------------------------------

# 🔐 What is OAuth 2.0?

OAuth 2.0 (Open Authorization) is an authorization framework that allows
third-party applications to access user resources without sharing the
user's username and password.

Instead of credentials, OAuth 2.0 uses an **Access Token**, making API
communication much more secure than Basic Authentication.

------------------------------------------------------------------------

# 🔄 OAuth 2.0 Authorization Code Flow

## Core Roles

  Role                   Description
  ---------------------- ------------------------------------------
  Resource Owner         User who owns the data
  Client                 Third-party application (Postman)
  Authorization Server   Authenticates the user and issues tokens
  Resource Server        Stores protected resources

## Flow

``` text
Client
   ↓
Authorization Server
   ↓
User Authentication
   ↓
Authorization Code
   ↓
Access Token
   ↓
Resource Server
```

### Steps

1.  Client sends an Authorization Request.
2.  User authenticates and grants permission.
3.  Authorization Server returns an Authorization Code.
4.  Client exchanges the code for an Access Token.
5.  Authorization Server returns the Access Token.
6.  Client accesses protected resources.

------------------------------------------------------------------------

# 🏗️ Project Architecture

``` text
Postman
   ↓
OAuth 2.0 Authentication
   ↓
Access Token
   ↓
Import Set API
   ↓
Import Set Table
   ↓
Transform Map
   ↓
Incident Table
```

------------------------------------------------------------------------

# 🎯 Objective

Create Incident records in ServiceNow securely from Postman without
directly inserting records into the Incident table.

------------------------------------------------------------------------

# ⚙️ Technologies Used

-   ServiceNow
-   OAuth 2.0
-   REST API
-   Import Set API
-   Transform Map
-   Postman

------------------------------------------------------------------------

# 📷 Step 1 --- Create Import Set Table

Navigation

``` text
System Web Services
   ↓
Inbound
   ↓
Import Sets
   ↓
Create New
```

**Actions Performed**

-   Created Import Set Table
-   Selected Incident as Target Table
-   Added required fields

**Purpose**

The Import Set Table acts as a staging table for incoming data.

<img src="image/import set table.png">

------------------------------------------------------------------------

# 📷 Step 2 --- Create Transform Map

Navigation

``` text
System Import Sets
   ↓
Transform Map
```

Configured Source Table and Target Table (Incident), then mapped
required fields.

<img src="image/Transform map.png">

------------------------------------------------------------------------

# 📷 Step 3 --- Configure OAuth 2.0

Navigation

``` text
System OAuth
   ↓
Application Registry
   ↓
New
```

Configured Client ID, Client Secret, Redirect URL, Authorization URL and
Token URL.

<img src="image/Postman application registry.png" width="1000">

------------------------------------------------------------------------

# 📷 Step 4 --- Configure Postman

Configured OAuth 2.0 authentication using Client ID, Client Secret,
Authorization URL and Token URL.

<img src="image/postman OAuth2.0 1.png">

------------------------------------------------------------------------

# 📷 Step 5 --- Generate Access Token & Call Import Set API

**Method**

``` text
POST
```

**Endpoint**

``` text
/api/now/import/u_inbound_incident_intergration
```

**Sample Request**

``` json
{
  "u_short_description":"TESTING AGAIN HIMA1234",
  "u_description":"TESTING AGAIN HIMA1134",
  "u_external_id":"ABCD123"
}
```


<img src="image/postman Oauth 2.0 2.png">

------------------------------------------------------------------------

# 📁 Repository Structure

``` text
📦 Postman-and-ServiceNow-Integration-With-OAuth-2.0
│── README.md
│── image
│   ├── import set table.png
│   ├── Transform map.png
│   ├── Postman application registry.png
│   ├── postman OAuth2.0 1.png
│   └── postman Oauth 2.0 2.png
│── Demo Viedo.mp4
```

------------------------------------------------------------------------

# 🎓 Learning Outcomes

-   OAuth 2.0 Authorization Code Flow
-   Import Set API
-   Transform Map
-   REST API
-   Secure Authentication
-   Postman API Testing
-   ServiceNow Integration

------------------------------------------------------------------------

# ⭐ Support

If you found this project helpful, consider giving the repository a ⭐
on GitHub.
