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
    dir('services/ui/angular') {
        stage('Dependencies') {
            docker.image('node:14.16').inside{
                sh 'npm ci --quiet --cache="./npm"'
            }
        }
        stage('Build'){
            echo 'Hello World From Imperative'
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