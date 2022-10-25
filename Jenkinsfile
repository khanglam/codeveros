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
    checkout scm
    stage('Clean Up') {
        cleanWs()
    }
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
        stage('Lint'){
            try {
                echo 'linting'
            } catch (Exception e) {
                echo 'Failed linting ' + e.toString()
            }
        }
    }
    
}