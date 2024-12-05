pipeline {
    agent any

    stages {
        stage('Git Cloning') {
            steps {
                echo 'Cloning git repo'
                git url: 'https://github.com/hakanbayraktar/flask-monitoring.git',  branch: 'main'
            }
        }
        
        stage('Integrate Remote kubernetess with Jenkins') {
            steps {

                    sh '''

                    ./kubectl get nodes
                    ./kubectl apply -f service.yaml
                    ./kubectl apply -f deployment.yaml
                    '''
                
            }
        }
    }
}
