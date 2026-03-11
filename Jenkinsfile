node {
    stage('RM Image') {
        sh '/usr/local/bin/docker rm -f nginx-test || true'
    }
    stage('Clone') {
        checkout scm 
    }
    stage('Build') {
        sh '/usr/local/bin/docker build -t xavki/nginx .'
    }
    stage('Test Image') {
        sh '/usr/local/bin/docker run -d -p 8080:80 --name nginx-test xavki/nginx'
    }
    stage('Check Container') {
        sh '/usr/local/bin/docker ps'
    }
    stage('Test with Curl') {
        sh 'curl http://localhost:8080'
    }
}