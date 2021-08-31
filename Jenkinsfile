pipeline {
    agent any
    stages {
        stage('Select') {
            matrix {
                axes {
                    axis {
                        name 'PLATFORM'
                        values 'linux', 'windows'
                    }
                    axis {
                        name 'ARCHITECTURE'
                        values '64', '32'
                    }
                }
                excludes {
                    exclude {
                        axis {
                            name 'PLATFORM'
                            values 'windows'
                        }
                        axis {
                            name 'ARCHITECTURE'
                            values '32'
                        }
                    }
                }
                stages {
                    stage('Build') {
                        steps {
                            echo "Do Build for ${PLATFORM} - ${ARCHITECTURE}"
                        }
                    }
                    stage('Test') {
                        steps {
                            echo "Do Test for ${PLATFORM} - ${ARCHITECTURE}"
                        }
                    }
                }
            }
        }
    }
}
