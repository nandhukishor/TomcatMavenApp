pipeline {
    agent any

    stages {
        stage('Build Started'){
            steps{
                //add script to send email 
                emailext body: '''For Project \'HelloJava\' the build process has been initiated. Do not reply because it is Jnekins generated auto email.''', subject: 'Build Started', to: 'gvreddy1265@gmail.com'
            }
        }
        
        stage('Clone') {
            steps {
               //add script here to clone github repository
               git branch: 'master',  url: https://github.com/vanireddi/TomcatMavenApp.git
            }
        }

     stage('compile'){
         steps{
             // add script here to git repository
             sh 'mvn compile'
            }
        }   
    }
 }

        
    

