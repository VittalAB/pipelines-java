pipeline {
    agent any

    tools {
        // Install the Maven version configured as "M3" and add it to the path.
        maven "M3"
    }

    stages {
        stage('Build and Analyse') {
            steps {
                // Get some code from a GitHub repository
                git branch:"main",
                    url : 'https://github.com/VittalAB/pipelines-java.git'

                // Run Maven on a Unix agent.
                sh "mvn clean verify sonar:sonar   -Dsonar.projectKey=Jenkins-Pipeline   -Dsonar.host.url=http://20.163.247.4:9000  -Dsonar.login=sqp_b361b019b4022a41bc05c60862e49f24a5349986"

                // To run Maven on a Windows agent, use
                // bat "mvn -Dmaven.test.failure.ignore=true clean package"
            }

        }
    }
}
