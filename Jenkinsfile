pipeline {
    agent { label 'Slave2' }
                 stages {
        stage('Checkout') {
            steps {
                sh 'rm -rf hello-world-war'
                sh 'git clone https://github.com/Harshithhkgowd96/hello-world-war.git'
            }
        }
        stage('Build') {
            steps {
                   sh 'cd hello-world-war'
                    sh 'mvn clean package'
            }
        }
        stage('Deploy') {
            steps {
                sh 'scp /root/opt/jenkins/workspace/pipeline_job/target/hello-world-war-1.0.0.war root@172.31.41.12:/opt/apache-tomcat-10.1.34/webapps/'
            }
        }
    }
   post {
        success {
            emailext(
                subject: "Build success",
                body: "Build is successful",
                to: 'harshithkngowda96@gmail.com'
            )
        }
    failure {
            emailext(
                subject: "Build failed",
                body: "Build was failed ",
                to: 'harshithkngowda96@gmail.com'
                )
        }
    }
}
