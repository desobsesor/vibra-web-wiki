---
slug: mongodb-in-cluster-cloud-with-migration-process
title: MongoDB in Cluster Cloud with Migration Process
description: One of the most repetitive processes is migrating relational and non-relational databases from our on-premises environment to a cloud environment.
authors: [desobsesor]
tags: [vibra, mongodb, cloud, migration]
---

🚀 **Step-by-Step Guide: Migrating MongoDB from Local to Atlas**

One of the most repetitive processes is migrating relational and non-relational databases from our on-premises environment to a cloud environment. This short post explains how to configure Atlas, create a backup, and restore a database in a basic migration process.

### 1️⃣ Prepare MongoDB Atlas
- **Create a Cluster**: If you haven't already, head over to MongoDB Atlas and set up a free cluster (M0). Follow this [guide](#) for detailed instructions.
- **User Configuration**: Set up a user with read/write permissions (e.g., migrator).
- **Network Access**: Add your current IP (or use 0.0.0.0/0 temporarily) in Network Access.

**Get the Atlas Connection String**:
- Navigate to your cluster in https://cloud.mongodb.com/ and click "Connect". 
- Choose "Connect your application".
- Copy the Connection String (e.g., `mongodb+srv://user:password@clusterxxx.mongodb.net/`).

### 2️⃣ Export Local Data with `mongodump`
- **Backup Data Locally**:
run the following command:
```bash
  mongodump --host localhost --port 27017 --db vibra-db --out C://Users/USER/Personal/mongodb_backups_vibra_2025
```
- **Restore Data to Cloud**:
run the following command:
```bash
  mongorestore --uri="mongodb+srv://username:Password@cluster0xxx.xxxx.mongodb.net/" C://Users/USER/Personal/mongodb_backups_vibra_2025/
```

**Vibra** is an academic app for students who want to validate and share their thoughts and experiences with other students.

<!-- truncate -->



