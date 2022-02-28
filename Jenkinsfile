
def dockerImage = 'ta2199/demo-jenkins-movies-store'

node ('workers'){
    stage('Checkout'){
        checkout scm
    }

    def imageTest = docker.build("${dockerImage}-test", "-f Dockerfile .")

    stage('Code Analysis'){
        imageTest.inside{
            sh 'npm run lint'
        }
    }

}


