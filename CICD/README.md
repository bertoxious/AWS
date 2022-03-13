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
