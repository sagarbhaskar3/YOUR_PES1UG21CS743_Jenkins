pipeline {
    agent any
    
    stages {
        stage('Build') {
            steps {
                script {
                    // Compile the .cpp code directly using a shell script
                    writeFile file: 'pes1ug21cs743.cpp', text: '#include <iostream>\n\nint main() {\n    std::cout << "Hello, Jenkins!";\n    return 0;\n}\n'
                    sh 'g++ -o my_executable pes1ug21cs743.cpp'
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
