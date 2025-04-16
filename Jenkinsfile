pipeline {
    agent any

    stages {
        stage('Print Directory Structure (excluding .git, .idea, etc.)') {
            steps {
                script {
                    sh '''
                        echo "Workspace Directory Tree (excluding .git, .idea):"

                        print_tree() {
                            find "$1" \\( -path "$1/.git" -o -path "$1/.idea" \\) -prune -o -print | sed -e "s;[^/]*/;|____;g;s;____|; |;g"
                        }

                        print_tree "$(pwd)"
                    '''
                }
            }
        }
    }
}