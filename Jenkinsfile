pipeline{
    agent { label 'JDK11'}
    triggers{
        cron('0 * * * *')
    }

    stages{
        stage(source code){
            steps{
                git url: 'https://github.com/DevopsMan2022/openmrs-core.git',
                branch: 'branch_develop1'
            }
        }
        stage(Build the code){
            steps{
                sh script: "mvan clean package"
            }
        }
        stage(Publish test results){
            steps{
                junit testResults: 'target/surefire-reports/*.xml'
            }
        }
    }
}