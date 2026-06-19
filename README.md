# 🚀 Working To NoSQL

### Multi-Model Database Analysis & High Availability Lab

This project was developed to study NoSQL database models used in modern data architectures in a hands-on way, analyze system behavior in the context of the CAP Theorem, and gain practical experience with High Availability concepts in distributed systems.

As part of the project, **Document**, **Column-Family**, **Key-Value**, and **Graph** data models were configured as isolated Docker-based services and analyzed comparatively.

---

## 🎯 Project Goals

* Understand the architectural differences between NoSQL data models
* Observe the principles of the CAP Theorem (Consistency, Availability, Partition Tolerance) in practice
* Examine replication and failover behavior in distributed systems
* Build a portable and isolated environment using Docker container architecture

---

## 🏗️ System Architecture

The system consists of independent services running inside Docker containers. Each database operates in its own isolated environment, while MongoDB is configured with a Replica Set structure to provide high availability.

---

## 🌐 Data Models and Technologies Used

| Database         | Data Model        | CAP Property                            |
| ---------------- | ----------------- | --------------------------------------- |
| MongoDB          | Document-Oriented | CP (Consistency & Partition Tolerance)  |
| Apache Cassandra | Column-Family     | AP (Availability & Partition Tolerance) |
| RiakKV           | Key-Value         | AP (High Availability)                  |
| Neo4j            | Graph             | ACID & Relationship-Oriented Querying   |

---

## 🧩 Service Details

### 1️⃣ MongoDB – Document Store

* **Structure:** 3-node Replica Set (`mongo1`, `mongo2`, `mongo3`)
* **Purpose:** Data consistency and high availability
* **Features:**

  * Automatic leader election
  * Failover mechanism
  * Replica synchronization

### 2️⃣ Apache Cassandra – Wide Column Store

* **Purpose:** Horizontal scalability and high write throughput
* **Features:**

  * Distributed architecture
  * Tunable consistency levels
  * Fault tolerance

### 3️⃣ Neo4j – Graph Database

* **Structure:** Native Graph Engine
* **Purpose:** Relationship-focused data analysis
* **Features:**

  * Cypher query language
  * Graph traversal optimization
  * ACID transactions

### 4️⃣ RiakKV – Key-Value Store

* **Purpose:** High availability and low-latency data access
* **Features:**

  * Distributed storage
  * Fault-tolerant architecture
  * Automatic data replication

---

## 🛠️ Setup and Running

### 📦 Requirements

* Docker
* Docker Compose
* Linux (Ubuntu recommended)

---

### ▶️ Starting the Services

#### MongoDB Replica Set

```bash
sudo docker start mongo1 mongo2 mongo3
```

#### Other NoSQL Services

```bash
sudo docker start cassandra-server
sudo docker start riak-server
sudo docker start neo4j-server
```

---

## 🔬 Concepts Demonstrated

* CAP Theorem
* Replication
* Failover
* High Availability
* Distributed Databases
* Docker Containerization
* NoSQL Data Models

---

## 📄 License

This project was developed for educational and research purposes.
