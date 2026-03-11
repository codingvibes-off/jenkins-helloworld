node {
    def app
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
    stage('Test with Curl') {
        steps {
            sh 'curl http://localhost:8080'
        }
    }
}
