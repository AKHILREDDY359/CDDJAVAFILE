pipeline {
    agent any

    tools {
        jdk 'JDK-21'
        maven 'Maven-3.9.11'
    }

    stages {
        stage('Checkout') {
            steps {
                echo 'Code already checked out from SCM'
            }
        }

        stage('Build') {
            steps {
                dir('cddjavafile') {
                    sh 'mvn clean package'
                }
            }
        }

        stage('Run') {
            steps {
                dir('cddjavafile') {
                    sh 'java -cp target/classes com.example.cddjava.App'
                }
            }
        }
    }
}
