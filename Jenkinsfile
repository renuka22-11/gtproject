pipeline {
    agent any

    stages {
        stage('SCM checkout') {
            steps{
                git branch: 'main', url: 'https://github.com/renuka22-11/gtproject.git' 
            }
        }
        stage ('Docker main_image build'){
            steps{
                sh '/usr/bin/docker image build -t smaranm/main_image .'
            }
        }
        stage ('Docker courses_image build'){
            steps{
                sh '/usr/bin/docker image build -t smaranm/courses_image ./courses'
            }
        }
        stage ('Docker gallery_image build'){
            steps{
                sh '/usr/bin/docker image build -t smaranm/gallery_image ./gallery'
            }
        }
        stage ('Docker staff_image build'){
            steps{
                sh '/usr/bin/docker image build -t smaranm/staff_image ./staff'
            }
        }
        stage ('Docker contactus_image build'){
            steps{
                sh '/usr/bin/docker image build -t smaranm/contact-us_image ./contact-us'
            }
        }
        stage ('Docker login'){
            steps{
                sh 'echo dckr_pat_ISxSPc2DrvgTXQmpCdR4ZqpwMl8 | /usr/bin/docker login -u smaranm --password-stdin'
            }
        }
        stage ('Docker main_image push'){
            steps{
                sh '/usr/bin/docker image push smaranm/main_image'
            }
        }
        stage ('Docker courses_image push'){
            steps{
                sh '/usr/bin/docker image push smaranm/courses_image'
            }
        }
        stage ('Docker gallery_image push'){
            steps{
                sh '/usr/bin/docker image push smaranm/gallery_image'
            }
        }
        stage ('Docker staff_image push'){
            steps{
                sh '/usr/bin/docker image push smaranm/staff_image'
            }
        }
        stage ('Docker contactus_image push'){
            steps{
                sh '/usr/bin/docker image push smaranm/contact-us_image'
            }
        }
        stage ('create containers'){
            steps{
                sh '/usr/bin/docker-compose up -d'
            }
        }
    }
}
