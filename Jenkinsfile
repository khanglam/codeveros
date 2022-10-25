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
    checkout
    stage('Build'){
        echo 'Hello World From Imperative'
    }
    stage('lint'){
        try {
            echo 'linting'
        } catch (Exception e) {
            echo 'Failed linting ' + e.toString()
        }
    }
}