```
pipeline {
    agent any
    
    stages {
        stage('hello') {
            steps {
                echo 'hello world'
            }
        }
    }

    post {
        always {
            script {
                def buildStatus = currentBuild.currentResult
                def buildUser = currentBuild.getBuildCauses('hudson.model.Cause$UserIdCause')[0]?.userId ?: 'Git User'
                
                emailext(
                    subject: "Pipeline ${buildStatus}: ${env.JOB_NAME} #${env.BUILD_NUMBER}",
                    body: """
                        <p>This is a Jenkins CI/CD pipeline status.</p>
                        <p><b>Project:</b> ${env.JOB_NAME}</p>
                        <p><b>Build Number:</b> ${env.BUILD_NUMBER}</p>
                        <p><b>Build Status:</b> ${buildStatus}</p>
                        <p><b>Started by:</b> ${buildUser}</p>
                        <p><b>Build URL:</b> <a href="${env.BUILD_URL}">${env.BUILD_URL}</a></p>
                    """,
                    to: 'rajesh45v@gmail.com, rajeshv0450@gmail.com',
                    from: 'rajesh45v@gmail.com',
                    replyTo: 'rajesh45v@gmail.com',
                    mimeType: 'text/html',
                )
            }
        }
    }
}

```

<img width="1785" height="387" alt="image" src="https://github.com/user-attachments/assets/1e59c976-8389-4c78-a2c7-9e0abeb06544" />

<img width="1898" height="767" alt="image" src="https://github.com/user-attachments/assets/ae57e275-47ae-4827-9e34-c4f6c59858ac" />

<img width="1888" height="567" alt="image" src="https://github.com/user-attachments/assets/3d149759-8e80-495d-bfa7-feea6a68c2d2" />

<img width="1740" height="620" alt="image" src="https://github.com/user-attachments/assets/924a8609-1328-47a8-a7c1-d2812ea33a0e" />

<img width="1912" height="463" alt="image" src="https://github.com/user-attachments/assets/d2839c32-23b4-4683-970b-32e53ac41951" />

```

pipeline {
    agent any
    
    stages {
        stage('hello') {
            steps {
                echo 'hello world'
            }
        }

        stage('hello1') {
            steps {
                sh 'mkdir raja'
            }
        }

        stage('hello2') {
            steps {
                sh 'mkdir raja'
            }
        }
    }

    post {
        always {
            script {
                def buildStatus = currentBuild.currentResult
                def buildUser = currentBuild.getBuildCauses('hudson.model.Cause$UserIdCause')[0]?.userId ?: 'Git User'
                
                emailext(
                    subject: "Pipeline ${buildStatus}: ${env.JOB_NAME} #${env.BUILD_NUMBER}",
                    body: """
                        <p>This is a Jenkins CI/CD pipeline status.</p>
                        <p><b>Project:</b> ${env.JOB_NAME}</p>
                        <p><b>Build Number:</b> ${env.BUILD_NUMBER}</p>
                        <p><b>Build Status:</b> ${buildStatus}</p>
                        <p><b>Started by:</b> ${buildUser}</p>
                        <p><b>Build URL:</b> <a href="${env.BUILD_URL}">${env.BUILD_URL}</a></p>
                    """,
                    to: 'rajesh45v@gmail.com, rajeshv0450@gmail.com',
                    from: 'rajesh45v@gmail.com',
                    replyTo: 'rajesh45v@gmail.com',
                    mimeType: 'text/html'
                )
            }
        }
    }
}
```


