pipeline {
    agent { label 'windows' }

    environment {
        MAVEN_OPTS = '-Dmaven.test.failure.ignore=true'
    }

    parameters {
        string(name: 'GIT_REPO_URL', defaultValue: '', description: 'URL of the Git repository')
        string(name: 'GIT_BRANCH', defaultValue: 'main', description: 'Branch to build from')
        string(name: 'MAVEN_GOALS', defaultValue: 'install', description: 'Maven goals to execute')
    }

    stages {
        stage('Checkout') {
            steps {
                // Ensure the GIT_REPO_URL parameter is provided
                script {
                    if (!params.GIT_REPO_URL) {
                        error 'GIT_REPO_URL parameter is required.'
                    }
                }

                // Checkout the code from the specified repository and branch
                git url: params.GIT_REPO_URL, branch: params.GIT_BRANCH
            }
        }

        stage('Build') {
            steps {
                // Build the Maven project with the specified goals
                sh "mvn ${params.MAVEN_GOALS}"
            }
        }

        stage('Package') {
            steps {
                // Package the project
                sh 'mvn package'
            }
        }
    }

    post {
        always {
            // Archive the build artifacts
            archiveArtifacts artifacts: '**/target/*.war', allowEmptyArchive: true
        }
    }
}






































# linux

echo baf08f87d26c48afe9c0a03a06cce4900711f9d7320380aee95efc0342abe5a1> secret-file & curl.exe -sO http://localhost:8080/jnlpJars/agent.jar & java -jar agent.jar -url http://localhost:8080/ -secret @secret-file -name "dhruv_win" -webSocket -workDir "C:\jenkins"




java -jar agent.jar -jnlpUrl http://<jenkins-master-url>:8080/computer/<agent-name>/slave-agent.jnlp -secret <secret-key> -workDir "<agent-work-dir>"


java -jar agent.jar -jnlpUrl http://localhost:8080/computer/dhruv_win/slave-agent.jnlp -secret baf08f87d26c48afe9c0a03a06cce4900711f9d7320380aee95efc0342abe5a1 -name "dhruv_win" -workDir "C:\jenkins"

java -jar agent.jar -jnlpUrl file:///C:/jenkins/slave-agent.jnlp -secret baf08f87d26c48afe9c0a03a06cce4900711f9d7320380aee95efc0342abe5a1 -workDir "C:\jenkins"




echo baf08f87d26c48afe9c0a03a06cce4900711f9d7320380aee95efc0342abe5a1> secret-file
curl.exe -sO http://192.168.0.113:8080/jnlpJars/agent.jar
java -jar C:\jenkins\agent.jar -url http://192.168.0.113:8080/ -secret @secret-file -name "dhruv_win" -webSocket -workDir "C:\jenkins"


curl.exe -sO http://192.168.0.113:8080/jnlpJars/agent.jar
java -jar C:\jenkins\agent.jar -url http://192.168.0.113:8080/ -secret baf08f87d26c48afe9c0a03a06cce4900711f9d7320380aee95efc0342abe5a1 -name "dhruv_win" -webSocket -workDir "C:\jenkins"
