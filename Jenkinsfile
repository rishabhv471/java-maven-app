// def gv

// pipeline {
//     agent any
//     stages {
//         stage("init") {
//             steps {
//                 script {
//                     gv = load "script.groovy"
//                 }
//             }
//         }
//         stage("build jar") {
//             steps {
//                 script {
//                     echo "building jar"
//                     //gv.buildJar()
//                 }
//             }
//         }
//         stage("build image") {
//             steps {
//                 script {
//                     echo "building image"
//                     //gv.buildImage()
//                 }
//             }
//         }
//         stage("deploy") {
//             steps {
//                 script {
//                     echo "deploying"
//                     //gv.deployApp()
//                 }
//             }
//         }
//     }   
// }


pipeline {

    agent any

    stages {


        stage("build"){

            steps{
                echo 'building the application'
            }
        }
        stage("test"){
            steps{
                echo 'testing the application..'
            }
        }
         stage("deploy"){
            steps{
                echo 'deploying the application..'
            }
        }

    }
}
