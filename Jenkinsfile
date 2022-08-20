pipeline {
 agent {
 node { label "maven" }
 }
 environment { QUAY = credentials('QUAY_USER') }
 stages {
stage('Deploy to PROD') {
 when { branch "main" }
 steps {
 sh """
 oc set image deployment home-automation \
 home-automation=quay.io/${QUAY_USR}/do400-deploying-lab:build-${BUILD_NUMBER} \
 -n ltvutb-deploying-lab-prod --record
 """
 }
}
 }
}
