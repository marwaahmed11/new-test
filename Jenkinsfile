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
                cat tgoba
                git add .
                git -c user.name="marwaahmed11" -c user.email="marwaahmed200126@gmail.com" commit -m "message"
                git remote add origin https://github.com/marwaahmed11/new-test.git
                git push origin main
                """
                
            }
        }
    }
}
