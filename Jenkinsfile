pipeline {
agent any

environment {
    DOCKER_IMAGE = "rajeshtutta123/hotstar_project_img"
}

stages {

    stage('GIT CHECKOUT') {
        steps {
            git branch: 'main',
            credentialsId: 'rajeshcred',
            url: 'https://github.com/rajeshtutta/HOTSTAR-Project.git'
        }
    }

    stage('BUILD') {
        steps {
            sh 'mvn clean package -DskipTests'
        }
    }
    stage('JENKINS TO NEXUS') {
        steps {
          withMaven(jdk: 'jdk21', maven: 'maven3', traceability: true) {
             sh 'mvn deploy'
}
        }
    }

}

}
