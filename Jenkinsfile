pipeline {
    agent any

    environment {
        // Define environment variables if needed
    }

    stages {
        stage('Checkout') {
            steps {
                // Checkout source code from Git
                git 'https://github.com/Rubini-S/ExtentReport_Project.git'
            }
        }
        stage('Build') {
            steps {
                // Build the project (e.g., using Maven)
                sh 'mvn clean install'
            }
        }
        stage('Test') {
            steps {
                // Execute automated tests
                sh 'mvn test'
            }
        }
        stage('Generate Extent Report') {
            steps {
                // Execute the script to generate Extent Report
                sh 'java -cp "path/to/extentreports.jar:C:\Users\rubin\eclipse-workspace\Selenium_S2_ExtentReport\src\test\java\utilities\ListenersDemo_Reports.java" com.your.package.GenerateExtentReport'
            }
        }
        stage('Publish Report') {
            steps {
                // Archive the report files
                archiveArtifacts 'C:\Users\rubin\eclipse-workspace\Selenium_S2_ExtentReport\extent.html'             
            }
        }
    }

    post {
        always {
            // Clean up or perform any necessary post-build actions
        }
    }
}
