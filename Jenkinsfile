pipeline {
    agent any
    stages {
        stage ('checkout code from git-hub') {
            steps {
                git 'https://github.com/santoshhreddy/game-of-life.git'
            }
        }
        stage ('build code with maven') {
            steps {
                sh 'mvn clean package'
            }
        }
        stage ('archive artifacts') {
            steps { 
                archiveArtifacts 'gameoflife-web/target/*.war'
        }
     }
        stage ('junit test reports') {
            steps {
                junit 'gameoflife-web/target/surefire-reports/*xml'
            }
        }


    }
    
}


