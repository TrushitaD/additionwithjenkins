pipeline {
    agent any
    triggers {
        cron('H/2 * * * *')  // Run every 2 minutes
    }
    stages {
        stage('Build') {
            steps {
                // Compile and run your Java program
                 'javac add.java'
                 'java add'
            }
        }
    }
}
