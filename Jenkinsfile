@Library("my-shared-lib") _

pipeline {
    agent {
        label "vibhus"
    }
    stages {
        stage("Cloning") {
            steps {
                clone("https://github.com/shishirsri14/django-notes-app.git", "main")
            }
        }
        stage("Build") {
            steps {
                docker_build("notes-app", "latest")
            }
        }
        stage("Deploy") {
            steps {
                docker_deploy("notes-app-container", "8000", "notes-app", "latest")
            }
        }
    }
}
