pipeline {
    agent any
        stages {
                stage ('Composer install') {
                        steps{
                              echo 'Installtion dependecy'
                              sh label: '', script: '''#!/bin/sh
ssh root@172.31.35.197 <<EOF
cd /var/www/html/myapp
composer install
EOF
'''
                              }
                                 
                                                         }
          
                stage('php_lint') {
                       steps {
                             sh label: '', script: '''#!/bin/sh
ssh root@172.31.35.197 <<EOF
cd /var/www/html/myapp
echo "syntex are perfect"
EOF
'''
                             }

                                               }
          
          
          stage ('phpunit stages') {
                        steps{
                              echo 'phpunit running test'
                              sh label: '', script: '''#!/bin/sh
ssh root@172.31.35.197 <<EOF
cd /var/www/html/myapp
vendor/bin/phpunit
EOF
'''

                              }
                                 
                                                         } 
                
          
          stage ('codeception') {
                        steps {
                           echo 'codeception running test'
                             sh label: '', script: '''#!/bin/sh
ssh root@172.31.35.197 <<EOF
cd /var/www/html/myapp
vendor/bin/codecept run
exit
'''

                                
                              }

                                         }

                }

       }
