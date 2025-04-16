pipeline {
    agent any

    stages {
        stage('Print Directory Structure (excluding hidden folders)') {
            steps {
                script {
                    sh '''
                        echo "Workspace Directory Tree (excluding hidden folders):"

                        print_tree() {
                            find "$1" \\( -path "*/.*" -prune \\) -o -print | sed -e "s;[^/]*/;|____;g;s;____|; |;g"
                        }

                        print_tree "$(pwd)"
                    '''
                }
            }
        }
    }
}