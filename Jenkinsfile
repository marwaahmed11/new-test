pipeline {
    agent  any
    stages {
        stage('CI') {
            steps {
                git branch: 'main', url: 'https://github.com/marwaahmed11/new-test'
                sh """
                echo "New content" > file
                sed -i 's/20.14/20.15/g' tgroba
                ls 
                pwd
                cat file 
                cat tgroba
                git add .
                git -c user.name="marwaahmed11" -c user.email="marwaahmed200126@gmail.com" commit -m "message"
                """    
            }
        }
        stage('Update Code') {
            steps {
                script {
                    git branch: "main", 
                        // credentialsId: "<your-credentials>", 
                    message: "Update code", 
                    push: true
                }
            }
        }
    }
}
