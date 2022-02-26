pipeline {
    agent {
        label 'san1'
    }
    stages {
        stage ('checkout code from git-hub') {
            steps {
                git 'https://github.com/santoshhreddy/game-of-life.git'
            }
        }
        stage ('build code with maven') {
            steps {
                sh 'maven clean package'
            }
        }
        stage ('archive artifacts') {
            steps { 
                archive 'gameoflife-web/target/*.war'
        }
     }
        stage ('junit test reports') {
            steps {
                junit 'gameoflife-web/target/surefire-reports'
            }
        }


    }
    
}


