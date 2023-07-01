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


// pipeline {

//     agent any

//     stages {


//         stage("build"){

//             steps{
//                 echo 'building the application'
//             }
//         }
//         stage("test"){
//             steps{
//                 echo 'testing the application..'
//             }
//         }
//          stage("deploy"){
//             steps{
//                 echo 'deploying the application..'
//             }
//         }

//     }
// }



pipeline {

    agent any
    tools{
        maven 'Maven'
    }

    stages {
        stage("build jar"){

            steps{
                echo 'building the application'
                sh 'mvn package'
            }
        }
        stage("build image "){
            steps{
                echo 'building the docker image...'
                withCredentials([usernamePassword(credentialsId: '8a21993c-d97c-45d6-bf17-53236919adc4' , passwordVariable: 'PASS' ,usernameVariable : 'USER')])
                    sh 'docker buit -t rishabhv471/test:test-1.0 .'
                    sh "echo $PASS | docker login - u $USER --password-stdin"
                    sh 'docker push rishabhv471/test:test-1.0'
            }
        }
         stage("deploy"){
            steps{
                echo 'deploying the application..'
            }
        }

    }
}
