pipeline {
    agent any
    
    stages {
        stage('Build') {
            steps {
                script {
                    // Intentional error: added a syntax error in the C++ code
                    writeFile file: 'pes1ug21cs741.cpp', text: '#include <iostream>\n\nint main() {\n    std::cout << "Hello, Jenkins!";\n    return 0;\n'
                    sh 'g++ -o my_executable pes1ug21cs741.cpp'
                }
            }
        }
        
        stage('Test') {
            steps {
                script {
                    // Print the output of the compiled .cpp file
                    sh './my_executable'
                }
            }
        }
        
        stage('Deploy') {
            steps {
                script {
                    // You can add deployment steps here if needed
                    echo 'Deployment steps go here'
                }
            }
        }
    }
    
    post {
        failure {
            echo 'pipeline failed'
        }
    }
}
