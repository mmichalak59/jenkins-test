pipeline {
agent any

stages {
stage('Info') {
steps {
echo "Galaz: ${env.GIT_BRANCH}"
echo "Build: ${env.BUILD_NUMBER}"
}
}
stage('Testy') {
when {
not { branch 'origin/master' }
}
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
echo "OK na galezi: ${env.GIT_BRANCH}"
}
failure {
echo 'BLAD! Sprawdz logi.'
}
}
}

