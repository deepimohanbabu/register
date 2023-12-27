pipeline {
    agent { label 'Jenkins-agent' }
    tools {
        jdk 'Java 17'
        maven 'Maven 3'
    }
    stages { 
        stage("Cleanup workspace") {
               steps {
               cleanWs()
               }
        }
        stage("Checkout from SCM") {
               steps {
                    git branch: 'main', credentialsId: 'github', url: 'https://github.com/deepimohanbabu/register.git'
                }
        }

       stage("Build application") {
          steps {
              sh "mvn clean package"
              }
       }
       stage("Test application") {
             steps {
                  sh "mvn test"
             }
       }

    }
}
