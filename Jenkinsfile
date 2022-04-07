pipeline {
  agent any
  stages {
    stage('Aprobacion Manual') {
      steps {
        echo 'Aprobacion manual'
      }
    }

    stage('Actualiza rest prod') {
      parallel {
        stage('Actualiza rest prod') {
          steps {
            echo 'rest'
          }
        }

        stage('Actualiza frontend prod') {
          steps {
            echo 'frontend'
          }
        }

      }
    }

    stage('Ejecutar migracion') {
      steps {
        echo 'Se levantÃ³ respaldo de la base de datos'
        echo 'Se ejecutaron las migraciones'
      }
    }

    stage('Mail') {
      steps {
        echo 'Se envió email notificando.'
      }
    }

  }
  environment {
    pruebas = 'pruebas'
    produccion = 'produccion'
  }
}