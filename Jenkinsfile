pipeline {
  agent any
  stages {
    stage('Cambio en Main') {
      steps {
        echo 'Se actualiz� la rama main'
      }
    }

    stage('Deploy BD Pruebas') {
      parallel {
        stage('Deploy BD Pruebas') {
          steps {
            echo 'Se deploy� la base de datos de prueba'
          }
        }

        stage('Deploy rest') {
          steps {
            echo 'se ejecut� el servidor REST'
          }
        }

      }
    }

    stage('Ejecutar migracion') {
      steps {
        echo 'Se levant� respaldo de la base de datos'
        echo 'Se ejecutaron las migraciones'
      }
    }

    stage('Pruebas REST') {
      steps {
        echo 'Se ejecutaron las pruebas REST'
      }
    }

    stage('Deploy Frontend') {
      steps {
        echo 'El front end ha sido desplegado'
      }
    }

    stage('Pruebas FrontEnd') {
      steps {
        echo 'Se ejecutaron las pruebas del frontend.'
      }
    }

    stage('Actualiza rest prod') {
      parallel {
        stage('Actualiza rest prod') {
          steps {
            echo 'Se actualiz� el servidor rest en producci�n.'
          }
        }

        stage('Actualiza frontend prod') {
          steps {
            echo 'Se actualiz� versi�n front end'
          }
        }

      }
    }

    stage('Migraciones prod') {
      steps {
        echo 'Se ejecutaron las actualizaciones en la bd de producci�n.'
      }
    }

  }
  environment {
    pruebas = 'pruebas'
    produccion = 'produccion'
  }
}