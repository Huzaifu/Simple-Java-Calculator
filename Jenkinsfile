pipeline{
    agent any
    tools{
        maven 'maven'
    }
    stages{
         stage("git_checkout") {  
           	    steps {  
               	    echo "cloning repository" 
               	    echo "repo cloned successfully"  
               	}  
             } 
        stage('Build') {
            steps {
                sh 'mvn clean package'
            }
        }
        stage('Deploy') {
            steps {
                sh 'scp target/*.jar user@server:http://localhost:8080'
            }
        }
    }
}
