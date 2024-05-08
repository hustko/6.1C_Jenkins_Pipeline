pipeline{
    agent any
    stages{
        stage('Build'){
            steps{
                echo"Building code with automation tool - Gradle"
            }
        }
        stage('Unit and Integration Test'){
            steps{
                echo"Running unit tests - JUnit"
                echo"Running integration tests - Selenium"
            }
            post{
                success{
                    mail to: "hustperera@gmail.com",
                    subject: "Unit and Integration Test status email",
                    body: "Unit and Integration Test was successful, the logs are attached herewith."
                }
            }
        }
        stage('Code Analysis'){
            steps{
                echo" Analysing code and ensuring industry standards are met- SonarQube"
            }
        }
        stage('Security Scan'){
            steps{
                echo"Performing security scan - OWASP Dependency-Check"
            }
            post{
                success{
                    mail to: "hustperera@gmail.com",
                    subject: "Security status email",
                    body: "Security scan was successful"
                }
            }
        }
        stage('Deploy to Staging'){
            steps{
                echo"Deploying application to staging server - AWS EC2"
            }
        }
        stage('Integration Tests on Staging'){
            steps{
                echo"Ensuring application functions in production enviorment - selenium webdriver, postman"
            }
            post{
                success{
                    mail to: "hustperera@gmail.com",
                    subject: "Integration Tests on Staging Enviornment status email",
                    body: "Integration Tests was successful on the staging enviornment"
                }
            }
        }
        stage('Deploy to Production'){
            steps{
                echo"Deploye application to production server - AWS EC2"
            }
        }
    }
}
