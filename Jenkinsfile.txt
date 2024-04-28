pipeline {
    agent any
    
    triggers {
        cron('*/2 * * * *')  // Run every 2 minutes
    }
    
    environment {
        JAVA_HOME = tool name: 'JDK', type: 'jdk'  // Use the configured JDK tool
    }
    
    stages {
        stage('Build') {
            steps {
                // Checkout source code from SCM (e.g., Git)
                checkout scm
                
                // Set PATH to include JDK/bin directory
                script {
                    def javaHome = env.JAVA_HOME
                    def javaBin = "${javaHome}\\bin"
                    env.PATH = "${javaBin};${env.PATH}"
                }
                
                // Compile Java program
                javac 'Addition.java'
                
                // Run Java program
                java 'Addition'
            }
        }
    }
}

