pipeline{
    agent any
    stages{
        stage('checkout the code from github'){
            steps{
                 git url: 'https://github.com/akash120895/Banking-java-project.git'
                 echo 'github url checkout'
            }
        }
        stage('codecompile with akash'){
            steps{
                echo 'starting compiling'
                sh 'mvn compile'
            }
        }
        stage('codetesting with akash'){
            steps{
                sh 'mvn test'
            }
        }
        stage('qa with akash'){
            steps{
                sh 'mvn checkstyle:checkstyle'
            }
        }
        stage('package with akash'){
            steps{
                sh 'mvn package'
            }
        }
        stage('run dockerfile'){
          steps{
               sh 'docker build -t myimg .'
           }
         }
        stage('port expose'){
            steps{
                sh 'docker run -dt -p 8091:8091 --name c000 myimg'
            }
        }   
    }
}
