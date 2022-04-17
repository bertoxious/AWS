# AWS CICD 
## Continuous Integration
```mermaid
graph LR
A[Push code to Code Repository] -->B[Get Code build and test]
    B --> C[Tell developer results of build]
    C -->A
```
## Continuous Delievery
```mermaid
graph LR
A[Code Repository] -->B[Build Server]
	B-->C[Deployment Server]
	C-->D[Application Server]
```

Tech Stack
Code - AWS Code Commit/ Github / Bitbucket
Build and Test - AWS CodeBuild/ Jenkins / Travis / Teamcity
Deploy - AWSCodeDeploy EC2Instances / ElasticBeanstalk
to orchestrate all these things we need AWS CodePipeline

**AWS COdeCommit** - storing our code 
**AWS CodePipeline** - automating our pipeline from code to Elastic Beanstalk
**AWS CodeBuild** - building and testing our code 
**AWS CodeDeploy** - deploying the code to EC2 instances(not Elastic Beanstalk)
**AWS CodeStar** - manage software development activities in one place 
**AWS CodeArtifact** - stoer, publih, and share software packages
**AWS CodeGuru** - automated code reviews using Machine Learning
<details>
	<summary><h2>AWS Code Commit</h2></summary>
	<br>
</details>
<details>
	<summary><h2>AWS Code Pipeline</h2></summary>
</details>
<details>
	<summary><h2>AWS Code Build</h2></summary>
</details>
<details>
	<summary><h2>AWS Code Deploy</h2></summary>
</details>
