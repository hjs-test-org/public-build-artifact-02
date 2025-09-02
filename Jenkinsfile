pipeline {
    agent any

    stages {
        stage('Build') {
            stages {
                stage('Compile') {
                    steps {
                        echo 'Compiling...'
                        sleep 10
                    }
                }
                stage('Package') {
                    steps {
                        echo 'Packaging...'
                        sleep 5
                    }
                }
            }
        }

        stage('Registering build artifact') {
            steps {
                echo 'Registering the metadata'
                echo 'Another echo to make the pipeline a bit more complex'
    
                // registerBuildArtifactMetadata(
                //     name: "test-deployment",
                //     version: "1.0.1",
                //     type: "docker",
                //     url: "http://localhost:4001",
                //     digest: "6f637064707039346163663237383761",
                //     // label: "Internal-demo-BT-artifact-Prod"
                // )
                
                registerBuildArtifactMetadata(
                    name: "test-deployment",
                    version: "1.0.0",
                    type: "docker",
                    url: "http://aws.artifacts/6a9acc6aa1be5446a2393ab90e7ca9e218bc07fa",
                    digest: "6a9acc6aa1be5446a2393ab90e7ca9e218bc07fa",
                    label: "123456789012345678901,test02"
                )
                // registerBuildArtifactMetadata(
                //     name: "prod-demo-runs-BT-branch-2",
                //     version: "1.0.1",
                //     type: "docker",
                //     url: "http://localhost:4001",
                //     digest: "6f637064707039346163663237383761",
                //     label: "Internal-demo-BT-artifact-Prod"
                // )
                // registerBuildArtifactMetadata(
                //     name: "test-deployment",
                //     version: "1.0.0",
                //     type: "docker",
                //     url: "http://aws.artifacts/6a9acc6aa1be5446a2393ab90e7ca9e218bc07fa",
                //     digest: "6a9acc6aa1be5446a2393ab90e7ca9e218bc07fa",
                //     label: "preprod,test"
                // )
            }
        }

        stage('Test') {
            steps {
                echo 'Running Unit Tests...'
                sleep 10
                echo 'Running Integration Tests...'
                sleep 5
            }
        }

        stage('Deploy') {
            steps {
                echo 'Deploying...'
                sleep 5
            }
        }
    }
}
