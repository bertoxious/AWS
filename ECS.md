# ECS - Elastic Container Service
## Amazon ECS - _EC2 Launch Type_
1. Launch Docker containers on AWS = Launch ECS Tasks on ECS Clusters
2. EC2 launch type : you must provision and maintain the infrastructure (The EC2 instances)
3. Each EC2 instance must run the ECS Agent to register in the ECS Cluster
4. AWS takes care if starting/ stopping containers

## Amazon ECS - _Fargate Launch Type_
1. Lauch Docker container on AWS
2. You do not provision the infrastructure (No EC2 instances to manage)
3. It's all serverless

