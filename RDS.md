## RDS (Relational Database Service)
Allows you to create databases in cloud managed by AWS
Postgres, MySQL, MariaDB, Oracle, Microsoft SQL Server, Aurora(AWS Propreitary Database)

#### Advantages :
- Automated provisioning : Automated provisioning means having the ability to deploy information technology or telecommunications services using predeﬁned automated procedures without requiring human interventions.
- OS Patching
- Continuous Backups and Restores to specific timestamp(Point in time restore)
- Monitoring Dashboards
- Multi A-Z support for Disaster Recovery
- Maintainence windows for upgrades
- Scaling Capability, Vertcal and Horizontal
- Storage backed by EBS

### Can't SSH into your instances

### RDS autmated backups
- Daily full backup
- Transaction logs backup after every 5 minutes
- 7 days retention period that can be upgraded to 35 days

#### Also have DB Snapshots that are manually triggered by user and retention of these backup snapshots as long as you want

#### RDS Read replicas for read scalability
- Read replicas helps to scale your reads
- We can create upto 5 read replicas, they can be within same Availaibility Zone, cross AZs or cross Region
- Replication is **ASYNC** so reads are eventually consistent 
- Read Replicas are used for ONLY READ STATEMENTS so even in a production database it won't effect the original contents

### Read replicas witin the same region no need to pay fee 
us-east-1a to us-east-1b is **FREE**
us-east-1a to eu-west-1b is **CHARGEABLE**

**Read Replicas can be setup across Mutiple Availaibility Zones for Disaster Recovery**

**No need to stop DB when switcing from Single AZ to Multiple AZ**
### Encryption
- Possible to encrypt master and read replicas with AWS KMS - AES 256 encryption
- Encryption has to be defined at launch time 
- If master is not encrypted, the read replicas cannot be encrypted
- Tranparent Data Encrption avaialaible for Oracle and SQL Server.
`
TDE does real-time I/O encryption and decryption of data and log files. The encryption uses a database encryption key (DEK). The database boot record stores the key for availability during recovery. The DEK is a symmetric key. It's secured by a certificate that the server's master database stores or by an asymmetric key that an EKM module protects.

TDE protects data at rest, which is the data and log files. It lets you follow many laws, regulations, and guidelines established in various industries. This ability lets software developers encrypt data by using AES and 3DES encryption algorithms without changing existing applications.
`

