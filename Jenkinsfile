pipeline{
        agent any
        stages{
            stage('Clone'){
                steps{
                    git clone https://gitlab.com/qacdevops/chaperootodo_client.git
                }
            }
            stage('Deploy'){
                sudo docker-compose pull && sudo -E DB_PASSWORD=${DB_PASSWORD} docker-compose up -d
            }
        }
}
