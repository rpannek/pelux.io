pipeline {
    agent {
        dockerfile {
            /* There are resolution issues on the Jenkins server for pelux.io */
            args "--add-host=pelux.io:${env.JENKINS_IP}"
        }
    }

    stages {
        stage('Download') {
            steps {
                // Delete old files
                sh 'rm -rf .[^.] .??* *'

                // Checkout the git repository and refspec pointed to by jenkins
                checkout scm
            }
        }

        // Configure the software
        stage('Configure') {
            steps {
                script {
                    sh "bundle install --path vendor/bundle"
                }
            }
        }

        stage("Build") {
            steps {
                sh "bundle exec jekyll build"
            }
        }

        stage("Test") {
            steps {
                sh "bundle exec htmlproofer --disable-external ./_site"
            }
        }

        stage('Archive') {
            steps {
                // Store the artifacts of the entire build
                archiveArtifacts artifacts: '_site/**/*', fingerprint: true
            }
        }
    }
}
