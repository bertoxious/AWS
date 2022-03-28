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
