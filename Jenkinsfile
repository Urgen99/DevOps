pipeline {
    agent any
    stages {
        stage('Buildapp') {
            steps {
                sh 'mvn -f jenkins/java-tomcat-sample/pom.xml clean package'
                echo "Running Unitest"
            }
            post {
                success {
                    echo "Archiving the Artifacts....."
                    archiveArtifacts artifacts: '**/*.war'
                }
            }
        }
        stage('Build') {
            steps {
                echo "Building the code"
            }
        }
        stage('DeployStaging') {
            steps {
                echo "Deploying to staging env"
            }
        }  
        stage('DeployProd') {
            steps {
                echo "Deploying to prod env"
            }
        }    
    }
}
