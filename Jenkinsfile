pipeline {
 agent {
 node { label "maven" }
 }
 environment { QUAY = credentials('QUAY_USER') }
 stages {
stage('Deploy to TEST') {
 when { not { branch "main" } }
 steps {
 sh """
 oc set image deployments home-automation \
 home-automation=quay.io/${QUAY_USR}/do400-deploying-lab:build-
${BUILD_NUMBER} \
 -n ltvutb-deploying-lab-test --record
 """
 }
}
 }
}
