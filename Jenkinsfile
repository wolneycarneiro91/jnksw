pipeline{
    agent any
    stages{

        stage("build"){
            steps{
                echo "Installing composer"
                sh 'curl -sS https://getcomposer.org/installer | php'
                sh 'mv composer.phar /usr/local/bin/composer'                                                              
            }
        }
        stage("deploy"){
            steps{
                echo "running artisans and composer clear"         
                sh 'php artisan optimize:clear'
                sh 'php artisan config:cache'
                sh 'composer dump-autoload'
                sh 'composer clear-cache'
                sh 'php artisan key:generate'
                sh 'php artisan migrate'
            }
        }                
    }

}
