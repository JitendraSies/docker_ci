pipeline{
    agent any
    stages{
        stage('1. Checkout'){
            steps{
                git url: 'https://github.com/JitendraSies/docker_ci.git'
            }
        }
        stage('2. Build Image') {
            steps{
                bat 'docker build -t mywebsite'
            }
        }
        stage('3. Stop/Remove old Containers') {
            steps{
                bat 'docker stop mycont || exit 0'
                bat 'docker rm mycont || exit 0'
            }
        }
        stage('Run the Image - Containerize') {
            steps{
                bat 'docker run -d -p 5000:80 --name mycont mywebsite'
            }
        }
    }
}
