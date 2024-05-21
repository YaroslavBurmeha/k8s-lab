pipeline {
	agent none

	stages {
		stage("build"){
			agent {
				label 'local'
			}
			steps{
				sh 'echo "Номер билда: "$BUILD_NUMBER'
				dir('k8s-lab'){
				    sh 'git pull'
				    sh 'docker build --no-cache -f dockerfiles/web/Dockerfile . -t 192.168.59.250:5000/app:$BUILD_NUMBER'
				    sh 'docker push 192.168.59.250:5000/app:$BUILD_NUMBER'
				}
			}
		}
		stage("test k8s"){
			agent {
				label 'k8s'
			}
			steps{
				sh 'git pull origin main'
				sh 'cp manifest.yaml manifest_prod.yaml'
				sh 'sed -i "s/BuildNumber/$BUILD_NUMBER/g" manifest_prod.yaml'
				sh 'cat manifest_prod.yaml | grep 192.168.59.250'
				sh 'kubectl apply -f manifest_prod.yaml'
				
			}
		}
	}
}
