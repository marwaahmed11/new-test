// https://docs.cloudbees.com/docs/cloudbees-ci-kb/latest/client-and-managed-controllers/pipeline-equivalent-to-git-publisher
pipeline {
    agent any
    stages {
        stage("Build") {
            steps {
                // Create a dummy file in the repo
                git branch: 'main', url: 'https://github.com/marwaahmed11/new-test'
                sh """
                echo "New content" > file
                echo "Hello" >> test-file
                sed -i 's/20.14/20.15/g' tgroba
                ls 
                pwd
                cat file 
                cat tgroba
               """
            }
        }
        stage("Commit") {
            steps {
                sh('''
                    git checkout -B main
                    git config user.name 'marwaahmed11'
                    git config user.email 'marwaahmed200126@gmail.com'
                    git add . && git commit -am "[Jenkins CI] Add build file"
                ''')
            }
        }
        stage("Push") {
            environment {
                GIT_AUTH = credentials('test')
            }
            steps {
                sh('''
                    git config --local credential.helper "!f() { echo username=\\$GIT_AUTH_USR; echo password=\\$GIT_AUTH_PSW; }; f"
                    git push origin HEAD:main
                ''')
            }
        }
    }
}
