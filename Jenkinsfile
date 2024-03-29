pipeline {
    agent any

    stages {
        stage('Build Docker Image') {
            steps {
                script {
                    // Build Docker image
                    sh 'pwd'
                    sh 'ls'
                    docker.build("falonnengass/my-docker-repo:new-imagev2.0", "/var/lib/jenkins/workspace/kub-jen-deploy/webapp")
                    // Replace "/path/to/Dockerfile" with the actual path to your Dockerfile
                    sh 'docker images'  
                }       
            }                
        }
        stage('Push Docker Image') {
            steps {
                script {
                    // Push Docker image to registry
                    docker.withRegistry('https://index.docker.io/v1/', 'dockerhub') {
                        docker.image('falonnengass/my-docker-repo:new-imagev2.0').push()   
                    }
                }
            }
        }
        stage('Deploy Kubernetes Manifest') {
            steps {
                script {
                    // Update kubeconfig for the EKS cluster
                    sh "aws eks --region us-east-2 update-kubeconfig --name van-cluster"
                    // Apply Kubernetes manifest file
                    sh 'kubectl apply -f deployservice.yaml'
                    sh 'kubectl apply -f service.yaml'
                    // sh 'kubectl apply -f deployservice.yaml -v=8'
                }
            }
        }
        stage('Verify Deployment') {
            steps {
                script {
                    // Verify deployment
                    sh "kubectl get nodes"
                    sh "kubectl get pods"
                    sh "kubectl get deployments"
                    sh "kubectl get services"
                    // Additional verification steps can be added here
                }
            }
        }
    }

    post {
        always {
            cleanWs()
        }
        success {
            echo "Pipeline succeeded!"
        }
        failure {
            echo "Pipeline failed!"
        }
    }
}





// pipeline {
//     agent any

//     stages {
//         stage('Build Docker Image') {
//             steps {
//                 script {
//                     // Build Docker image; 
//                     sh 'pwd'
//                     sh 'ls'
//                     docker.build("falonnengass/my-docker-repo:new-imagev1.0", "/var/lib/jenkins/workspace/new-pipeline")
//                     // Replace "/path/to/Dockerfile" with the actual path to your Dockerfile
//                     sh 'docker images'
//                 }       
//             }                
//         }
//         stage('Push Docker Image') {
//             steps {
//                 script {
//                     // Push Docker image to registry
//                     docker.withRegistry('https://index.docker.io/v1/', '047d29ec-89d1-46ba-a33d-ac41961ea266') {
//                         docker.image('falonnengass/my-docker-repo:new-imagev1.0').push()   
//                     }
//                 }
//             }
//         }
//         stage('Deploy Kubernetes Manifest') {
//             steps {
//                 script {
//                      // Update kubeconfig for the EKS cluster
//                     sh "aws eks --region us-east-1 update-kubeconfig --name my-cluster"
//                     // Apply Kubernetes manifest file
//                     sh 'kubectl apply -f deployservice.yaml'
//                 }
//             }
//         }
//     }
// }
//        stage('Verify Deployment') {
//            steps {
//                script {
//                    sh "kubectl get nodes"
//                    sh "kubectl get pods"
//                    sh "kubectl get deployments"
//                    sh "kubectl get services"
//           // Additional verification steps can be added here
//         }
//       }
//     }
//   }

//   post {
//     always {
//       cleanWs()
//     }
//     success {
//       echo "Pipeline succeeded!"
//     }
//     failure {
//       echo "Pipeline failed!"
//     }
//   }
// }




// pipeline {
//     agent any

//     stages {
//         stage('Build Docker Image') {
//             steps {
//                 script {
//                     // Build Docker image
//                     sh 'pwd'
//                     sh 'ls'
//                     docker.build("falonnengass/my-docker-repo:new-imagev1.0}", "/var/lib/jenkins/workspace/new-pipeline")
//                     // sh 'docker build -t fal-hub-image .'
//                     sh 'docker images'
//                 }       
//             }                
//         }
//         stage('Push Docker Image') {
//             steps {
//                 script {
//                     // Push Docker image to registry
//                     docker.withRegistry('https://index.docker.io/v1/', '047d29ec-89d1-46ba-a33d-ac41961ea266') {
//                         docker.image('falonnengass/my-docker-repo:new-imagev1.0').push()   
//                     }
//                 }
//             }
//         }
//         stage('Deploy Kubernetes Manifest') {
//             steps {
//                 script {
//                     // Apply Kubernetes manifest file
//                     sh 'kubectl apply -f deployservice.yaml'
//                 }
//             }
//         }
//     }
// }









// // pipeline {
// //     agent any

// //     stages {
// //         stage('Build Docker Image') {
// //             steps {
// //                 script {
// //                     // Build Docker image
// //                     sh 'docker build -t fal-hub-image:v2.0 .'

// //                     sh 'docker images'
// //                 }       
// //             }                
// //         }
// //         stage('Push Docker Image') {
// //             steps {
// //                 script {
// //                     // Push Docker image to registry
// //                     docker.withRegistry('https://index.docker.io/v1/', '047d29ec-89d1-46ba-a33d-ac41961ea266') {
// //                         docker.image('falonnengass/my-docker-repo:fal-hub-image).push()   
// //                     }
// //                 }
// //             }
// //         }
// //         stage('Deploy Kubernetes Manifest') {
// //             steps {
// //                 script {
// //                     // Apply Kubernetes manifest file
// //                     sh 'kubectl apply -f deployservice.yaml'
// //                 }
// //             }
// //         }
// //     }































// pipeline {
//     agent any

//     stages {
//         stage('Build Docker Image') {
//             steps {
//                 script {
//                     // Build Docker image
//                     sh 'docker build -t fal_hub_image:v2.0 .'

//                     sh 'docker images'
//                 }       
//             }                
//         }
//         stage('Push Docker Image') {
//             steps {
//                 script {
//                     // Push Docker image to registry
//                     docker.withRegistry('https://index.docker.io/v1/', '047d29ec-89d1-46ba-a33d-ac41961ea266') {
//                         docker.image('falonnengass/my-docker-repo:fal-hub-image:v2.0').push()
//                     }
//                 }
//             }
//         }
//         stage('Deploy Kubernetes Manifest') {
//             steps {
//                 script {
//                     // Apply Kubernetes manifest file
//                     sh 'kubectl apply -f deployservice.yaml'
//                 }
//             }
//         }
//     }
// }









// pipeline {
//     agent any

//     stages {
//         stage('Build Docker Image') {
//             steps {
//                 script {
//                     // Build Docker image
//                     sh 'docker build -t fal-hub-image:v2.0 .'
//                     sh 'docker images'
//                 }       
//             }                
//         }
//         stage('Push Docker Image') {
//             steps {
//                 script {
//                     // Push Docker image to registry
//                     // withDockerRegistry([credentialsId:'047d29ec-89d1-46ba-a33d-ac41961ea266', url: 'https://index.docker.io/v1/']) {
//                     //     sh 'docker push falonnengass/my-docker-repo:fal-hub-imagev2.0'
//                     docker.withRegistry('https://index.docker.io/v1/', '047d29ec-89d1-46ba-a33d-ac41961ea266') {
//                         docker.image falonnengass/my-docker-repo:fal-hub-imagev1.push()
//                     }
//                 }
//             }
//         }
//         stage('Deploy Kubernetes Manifest') {
//             steps {
//                 script {
//                     // Apply Kubernetes manifest file
//                     sh 'kubectl apply -f deployservice.yaml'
//                 }
//             }
//         }
//     }
// }




// pipeline {
//     agent any // or { agent { label 'docker && kubernetes' } }

//     stages {
//         stage('Build Docker Image') {
//             steps {
//                 script {
//                     // Build Docker image
//                     sh 'docker build -t my-docker-repo/fal-hub-image:v2.0 .' //or docker build -t fal-hub-image?
//                 }       

//             }
//         }
//         stage('Push Docker Image') {
//             steps {
//                 script {
//                     // Push Docker image to registry
//                     withDockerRegistry([credentialsId: '047d29ec-89d1-46ba-a33d-ac41961ea266', url: "https://index.docker.io/v1/"]) {
//                         sh 'docker push falonnengass/my-docker-repo:fal-hub-image:v2.0'      
//                     }
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
// }











   











// pipeline {
//     agent any // or { agent { label 'docker && kubernetes' } }

//     stages {
//         stage('Build Docker Image') {
//             steps {
//                 script {
//                     // Build Docker image
//                     sh 'docker build -t my-docker-repo/fal-hub-image:v2.0 .' //or docker build -t fal-hub-image?
//                 }       

//             }
//         }
//         stage('Push Docker Image') {
//             steps {
//                 script {
//                     // Push Docker image to registry
//                     sh 'docker push falonnengass/my-docker-repo:fal-hub-image:v2.0'      
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
// }

// withDockerRegistry([credentialsId: '047d29ec-89d1-46ba-a33d-ac41961ea266', url: "https://index.docker.io/v1/" //url is the URL of all docker regitry images
//                         docker.image "fal-hub-image"falonnengass/my-docker-repo:fal-hub-image").push()





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
