# 🚀 Working To NoSQL  
## Multi-Model Database Analysis & High Availability Lab

Bu proje, modern veri mimarilerinde kullanılan **NoSQL veri tabanı modellerini** uygulamalı olarak incelemek, **CAP Teoremi** kapsamında sistem davranışlarını analiz etmek ve dağıtık sistemlerde **yüksek erişilebilirlik (High Availability)** kavramlarını deneyimlemek amacıyla geliştirilmiştir.

Proje kapsamında **Document, Column-Family, Key-Value ve Graph** veri modelleri, Docker tabanlı izole servisler üzerinde yapılandırılmış ve karşılaştırmalı olarak analiz edilmiştir.

---

## 🎯 Projenin Amacı

- NoSQL veri modellerinin mimari farklarını kavramak  
- CAP Teoremi (Consistency, Availability, Partition Tolerance) prensiplerini uygulamalı gözlemlemek  
- Dağıtık sistemlerde replikasyon ve failover davranışlarını incelemek  
- Docker konteyner mimarisi ile taşınabilir ve izole bir çalışma ortamı oluşturmak  

---

## 🏗️ Sistem Mimarisi

Sistem, **Docker konteynerları** üzerinde çalışan birbirinden bağımsız servislerden oluşmaktadır. Her veritabanı kendi izole ortamında çalışmakta olup, MongoDB özelinde **Replica Set** yapısı kurulmuştur.

### 🌐 Kullanılan Veri Modelleri ve Teknolojiler

| Veritabanı | Veri Modeli | CAP Özelliği |
|------------|------------|--------------|
| **MongoDB** | Document-Oriented | **CP** (Consistency & Partition Tolerance) |
| **Apache Cassandra** | Column-Family | **AP** (Availability & Partition Tolerance) |
| **RiakKV** | Key-Value | **AP** (High Availability) |
| **Neo4j** | Graph | **ACID** & İlişki Odaklı Sorgulama |

---

## 🧩 Servis Detayları

### 1️⃣ MongoDB – Document Store
- **Yapı:** 3 Node Replica Set (`mongo1`, `mongo2`, `mongo3`)
- **Amaç:** Veri tutarlılığı ve yüksek erişilebilirlik
- **Özellik:** Otomatik lider seçimi (Election) ve failover mekanizması

### 2️⃣ Apache Cassandra – Wide Column Store
- **Amaç:** Yatay ölçeklenebilirlik ve yüksek yazma performansı

### 3️⃣ Neo4j – Graph Database
- **Yapı:** Native Graph Engine
- **Amaç:** İlişkisel veri analizleri ve Cypher sorgu dili ile graph işlemleri

### 4️⃣ RiakKV – Key-Value Store
- **Amaç:** Yüksek erişilebilirlik ve düşük gecikmeli veri erişimi

---

## 🛠️ Kurulum ve Çalıştırma

### 📦 Gereksinimler
- Docker
- Docker Compose
- Linux (Ubuntu önerilir)

### ▶️ Servisleri Başlatma

# MongoDB Replica Set
sudo docker start mongo1 mongo2 mongo3

# Diğer NoSQL Servisleri
sudo docker start cassandra-server riak-server neo4j-server
