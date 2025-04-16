pipeline {
    agent any

    stages {
        stage('Print Directory Structure') {
            steps {
                script {
                    // Create a shell script to print the directory structure
                    sh '''
                        echo "Workspace Directory Tree:"
                        print_tree() {
                            find "$1" -print | sed -e "s;[^/]*/;|____;g;s;____|; |;g"
                        }

                        print_tree "$(pwd)"
                    '''
                }
            }
        }
    }
}