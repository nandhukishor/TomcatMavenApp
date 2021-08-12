pipeline {
    agent any

    stages {
        
        
        stage('Clone') {
            steps {
               //add script here to clone github repository
               git branch: 'master', url: 'https://github.com/nandhukishor/TomcatMavenApp.git'
            }
        }
        
        stage('Compile'){
            steps{
                //add script here to compile the maven project
                sh 'mvn clean compile'
            }
        }
        
        stage('Test'){
            steps{
                //add a step to run the maven tests
                sh 'mvn clean test'
            }
        }
        
        stage('Package'){
            steps{
                //add a step to pacakge jar file
                sh 'mvn clean package'
            }
        }
        
        stage('Publish to Nexus'){
            steps{
                //add a script to publish jar file into Nexus Repository
                sh 'mvn -s ./settings.xml deploy'
            }
        }
         stage('Deploy to Tomcat'){
            steps{
                //add a script to deploy jar file into Tomcat
                sh 'mvn -s ./settings.xml tomcat7:deploy'
            }
        }
    }
}
