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
                sh '${MAVEN_HOME} clean compile'
            }
        }
        
        stage('Test'){
            steps{
                //add a step to run the maven tests
                sh '${MAVEN_HOME} clean test'
            }
        }
        
        stage('Package'){
            steps{
                //add a step to pacakge jar file
                sh '${MAVEN_HOME} clean package'
            }
        }
        
        stage('Publish to Nexus'){
            steps{
                //add a script to publish jar file into Nexus Repository
                sh '${MAVEN_HOME} -s ./settings.xml deploy'
            }
        }
    }
}
