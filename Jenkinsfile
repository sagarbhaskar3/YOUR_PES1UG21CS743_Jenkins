pipeline {
    agent any

    stages {
        stage('Prepare') {
            steps {
                script {
                    // Create the C++ file
                    writeFile file: 'PES1UG21CS743.cpp', text: '''
                    #include <iostream>
                    using namespace std;
                    
                    int main() {
                        cout << "Hello, world!" << endl;
                        return 0;
                    }
                    '''
                }
            }
        }
        
        stage('Build') {
            steps {
                sh 'g++ -o YOUR_SRN-1 PES1UG21CS743.cpp'
            }
        }
        
        stage('Test') {
            steps {
                sh './YOUR_SRN-1'
            }
        }
        
        stage('Deploy') {
            steps {
                // Add deployment steps here if needed
            }
        }
    }

    post {
        failure {
            echo 'pipeline failed'
        }
    }
}
