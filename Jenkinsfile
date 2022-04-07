pipeline {
  agent any
  stages {
    stage('Cambio en Main') {
      steps {
        echo 'Se actualizó la rama main'
      }
    }

    stage('Deploy BD Pruebas') {
      parallel {
        stage('Deploy BD Pruebas') {
          steps {
            echo 'Se deployó la base de datos de prueba'
          }
        }

        stage('Deploy rest') {
          steps {
            echo 'se ejecutó el servidor REST'
          }
        }

      }
    }

    stage('Ejecutar migracion') {
      steps {
        echo 'Se levantó respaldo de la base de datos'
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

    stage('Mail') {
      steps {
        echo 'Se envi� email notificando.'
      }
    }

  }
  environment {
    pruebas = 'pruebas'
    produccion = 'produccion'
  }
}