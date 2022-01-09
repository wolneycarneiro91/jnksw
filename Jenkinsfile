pipeline{
    agent any
    stages{

        stage("build"){
            steps{
                echo "Installing composer and laravel"
                sh 'curl -sS https://getcomposer.org/installer | php'
                sh 'mv composer.phar /usr/local/bin/composer'
                sh 'curl -s "https://laravel.build/judge-app?with=pgsql,redis" | bash'
                sh 'php artisan --version'
            }
        }
        stage("deploy"){
            steps{
                echo "running migrations"
                sh 'php artisan migrate'
            }
        }                
    }

}
