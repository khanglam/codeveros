// Declarative
//pipeline {
//     agent any

//     stages {
//         stage('Hello') {
//             steps {
//                 echo 'Hello World, this is Khang - testing autobuild'
//             }
//         }
//     }
// }

// Scripted/Imperative
node {
    stage('Clean Up') {
        cleanWs()
    }
    checkout scm
    dir('services/ui/angular') {
        stage('Dependencies') {
            docker.image('node:14.16').inside{
                sh 'npm ci --quiet --cache="./npm"'
            }
        }
        stage('Build'){
            docker.image('node:14.16').inside{
                sh 'npm run build.production --cache="./npm"'
            }
        }
        /*
        stage('Lint'){
            try {
                echo 'linting'
            } catch (Exception e) {
                echo 'Failed linting ' + e.toString()
            }
        }
        stage('Test'){  
            docker.image('buildkite/puppeteer:8.0.0').inside{
                sh 'npm run test --cache="./npm"'
            }
        }
        */
    }
    
}