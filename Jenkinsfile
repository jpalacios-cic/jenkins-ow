pipeline {
    agent any
    stages {
        stage('Obtener el repositorio') {
          steps {
              git branch: 'main', url: 'https://github.com/jpalacios-cic/jenkins-ow.git'
          }
        }
        stage('Generar la documentación') {
            steps {
                sh "doxygen"
            }
        }
    }
    post {
	success {
        	publishHTML([allowMissing: false, alwaysLinkToLastBuild: false, keepAll: false, reportDir: 'html/', reportFiles: 'files.html', reportName: 'Documentación', reportTitles: ''])
	}
    }
}
