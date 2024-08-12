pipeline{
    agent any
    stages{
        stage('checkout the code from github'){
            steps{
                 git url: 'https://github.com/Tamil1011/star-agile-banking-finance.git'
                 echo 'github url checkout'
            }
        }
        stage('codecompile with tamil'){
            steps{
                echo 'starting compiling'
                sh 'mvn compile'
            }
        }
        stage('codetesting with tamil'){
            steps{
                sh 'mvn test'
            }
        }
        stage('qa with tamil'){
            steps{
                sh 'mvn checkstyle:checkstyle'
            }
        }
        stage('package with tamil'){
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
