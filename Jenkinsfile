pipeline{
    agent any
    stages{
        stage('Build'){
            steps{
                sh 'mvn clean package'
            }
        }
        stage('Deploy to container'){
            steps{
                deploy adapters: [tomcat7(credentialsId: 'deployer1', path: '', url: 'http://ec2-3-141-167-51.us-east-2.compute.amazonaws.com:8080')], contextPath: 'javawebapp2', war: '**/java-web-project.war'
            }
        }
    }
}
