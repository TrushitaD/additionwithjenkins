pipeline {
    agent any
    
    triggers {
        cron('H/2 * * * *')  // Run every 2 minutes
    }
    
    stages {
        stage('Build') {
            steps {
                // Checkout source code from SCM (e.g., Git)
                git url: 'https://github.com/your/repository.git'
                
                // Set JDK environment (adjust tool name based on your Jenkins configuration)
                tool 'JDK'  // Use the configured JDK tool (replace 'JDK' with your tool name)
                
                // Compile Java program
                sh 'javac add.java'
                
                // Run Java program
                sh 'java add'
            }
        }
    }
}

