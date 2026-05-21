iipipeline {

    agent any

    stages {

        stage('Clone') {

            steps {
                git 'https://github.com/username/jenkins-cicd-project.git'
            }

        }

        stage('Build Docker') {

            steps {
                sh 'docker build -t flask-app .'
            }

        }

        stage('Deploy Container') {

            steps {

                sh 'docker stop flask-container || true'

                sh 'docker rm flask-container || true'

                sh 'docker run -d -p 80:5000 --name flask-container flask-app'

            }

        }

    }

}
