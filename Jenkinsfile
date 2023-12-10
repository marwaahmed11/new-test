pipeline {
    agent  any
    stages {
        stage('CI') {
            steps {
                git branch: 'main', url: 'https://github.com/marwaahmed11/new-test'
                sh """
                echo "New content" > file
                sed -i 's/20.14/20.15/g' 'new test'
                ls 
                pwd
                cat file 
                cat 'new test'
                git add .
                git commit -m "Modify file"
                git push origin main
                """
                
            }
        }
    }
}
