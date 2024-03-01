pipeline{
    agent { label 'jenkins-Agent' }
    tools {
        jdk 'Java17'
        maven 'Maven3'
    }
    stages{
        stage("cleanup Workspace")
        steps{
            cleanWs()
        }

    }

    stage ("CheckOut from SCM"){
        steps {
            git branch: 'master', credentials: 'github', url: 'https://github.com/sumitgupta190a/master_app.git'
        }
    }
    stage("Build Application"){
        steps {
            sh ("mvn clear package") {
                
            }
        }

        stage{"Test Application"} (
            steps {
                sh "mvn test"
            }
        )
    }
}
