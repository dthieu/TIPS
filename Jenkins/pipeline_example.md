```sh
	pipeline {
		agent any
		stages {
			stage ('build') {
				...
			}
			stage ('test: integration-&-quality') {
				...
			}
			stage ('test: functional') {
				...
			}
			stage ('test: load-&-security') {
				...
			}
			stage ('approval') {
				...
			}
			stage ('deploy:prod') {
				agent { label 'DEPLOY_PC' } // perform stage "deploy:prod" in DEPLOY_PC
				...
			}
		}
	}
```
