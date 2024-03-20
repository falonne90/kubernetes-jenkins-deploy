pipeline {
    agent any // or { agent { label 'docker && kubernetes' } }

    stages {
        stage('Build Docker Image') {
            steps {
                script {
                    // Build Docker image
                    sh 'docker build -t my-docker-repo:fal-hub-image v1.0' //or docker build -t fal-hub-image?
                }
            }
        }
        stage('Push Docker Image') {
            steps {
                script {
                    // Push Docker image to registry
                    sh 'docker push falonnengass/my-docker-repo:fal-hub-image'
                }
            }
        }
        stage('Deploy Kubernetes Manifest') {
            steps {
                script {
                    // Apply Kubernetes manifest file
                    sh 'kubectl apply -f deployservice.yaml'
                    // sh 'kubectl apply -f centos-app-service.yaml'
                }
            }
        }
    }
}







// pipeline {
//     agent any // or {agent { label 'docker && kubernetes'
//     }

//     stages {
//         stage('Build Docker Image') {
//             steps {
//                 script {
//                     // Build Docker image
//                     sh 'docker build -t my-docker-repo:fal-hub-image v1.0' //or docker build -t fal-hub-image?
//                 }
//             }
//         }
//         stage('Push Docker Image') {
//             steps {
//                 script {
//                     // Push Docker image to registry
//                     sh 'docker push falonnengass/my-docker-repo:fal-hub-image'
//                 }
//             }
//         }
//         stage('Deploy Kubernetes Manifest') {
//             steps {
//                 script {
//                     // Apply Kubernetes manifest file
//                     sh 'kubectl apply -f deployservice.yaml'
//                     // sh 'kubectl apply -f centos-app-service.yaml'
//                 }
//             }
//         }
//     }
