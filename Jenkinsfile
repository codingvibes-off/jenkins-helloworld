node {
    def app
    stage('Clone') {
        checkout scm 
    }
    stage('Build') {
        sh '/usr/local/bin/docker build -t xavki/nginx .'
    }
    stage('Test Image') {
        sh '/usr/local/bin/docker run -d -p 8080:80 --name nginx-test xavki/nginx'
    }
}
