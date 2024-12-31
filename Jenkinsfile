pipeline {
    parameters {
        string(name: 'cmd', defaultValue: 'package', description: 'Who should I say hello to?')

        choice(name: 'ch', choices: ['One', 'Two', 'Three'], description: 'Pick something')
    }
    agent any
       stages 
    {
        stage('checkout') {        
                        steps {
                            sh 'rm -rf hello-world-war'
                sh 'git clone https://github.com/sharanya123-ty/hello-world-war/'
            }
        }
         stage('build') { 
            steps {
                sh 'cd hello-world-war'
                sh 'mvn clean $cmd'
            }
        }
    }
}