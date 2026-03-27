pipeline {
agent any
environment {
APLIKACJA = 'Kalkulator'
WERSJA = '1.1.0'
}
stages {
stage('Info') {
steps {
echo "${env.APLIKACJA} v${env.WERSJA}"
echo "Build: ${env.BUILD_NUMBER}"
}
}
stage('Przygotowanie') {
steps {
sh 'python3 --version'
}
}
stage('Testy') {
steps {
sh 'python3 app_test.py'
}
}
stage('Aplikacja') {
steps {
sh 'python3 app.py'
}
}
}
post {
success {
echo "${env.APLIKACJA} v${env.WERSJA} - SUKCES"
echo "AUTOMAT!!!!"
}
failure {
echo "${env.APLIKACJA} - BLAD!"
}
}
}
