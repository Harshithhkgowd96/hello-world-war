pipeline {
    parameters {
        string(name: 'cmd', defaultValue: 'package', description: 'Who should I say hello to?')

        choice(name: 'ch', choices: ['One', 'Two', 'Three'], description: 'Pick something')
    }
    agent any
    stages {
        stage('checkout') {
            steps {
                sh 'git clone https://github.com/Harshithhkgowd96/hello-world-war/'
            }
        }
        stage('build') {
            steps {
                sh 'cd hello-world-war'
                sh '$cmd' 
            }
        }
    }
}
