pipeline{
    agent any
    stages{

        stage("build"){
            steps{
                echo "Installing laravel"
                sh 'composer install'
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
