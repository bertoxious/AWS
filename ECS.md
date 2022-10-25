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
4. You just create Task Definitions
5. AWS just runs ECS Tasks for you based on the CPU/ RAM you need
6. To scale, just increase the number of tasks. Simple - no more EC2 instances

## Amazon ECS - _IAM Roles for ECS_
1. EC2 Instance Profile(EC2 Launch Type Only):
  1. Used By ECS Agent
  2. Makes API calls to ECS Service
  3. Send cntainer logs to Cloudwatch logs
  4. PUll DOcker image form ECR
  5. Reference sensitive data in secrets manager or SSM parameter store
2. ECS Task Role
  1. Allows each task to have a specific role
  2. Use different roles for the different ecs services you run
  3. Task Role is defined in Task Definition

## Amazon ECS - _Load Balancer Integrations_
Application Load Balancer, Network Load Balancer, Elastic Load Balancer 

## Amazon ECS - _Data Volumes(EFS)_
1. Mount EFS fiels system onto ECS Tasks
2. Works for both EC2 and Fargae launch types.
3. FARGATE + EFS = SERVERLESS
