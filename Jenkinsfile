node {
    tools {
        nodejs 'NodeJS'
    }

    stage('Checkout') {
        checkout scm
    }

    stage('Install Dependencies') {
        sh 'npm install'
    }

    stage('Run Tests') {
        sh 'npm test -- --watchAll=false'
    }

    stage('Build') {
        sh 'npm run build'
    }

    stage('Archive Artifacts') {
        archiveArtifacts artifacts: 'build/**', fingerprint: true
    }
}
