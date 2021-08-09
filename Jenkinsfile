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
        
    }
}
