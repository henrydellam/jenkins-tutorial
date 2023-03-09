pipeline{
        agent any
        stages{
            stage('Clone'){
                steps{
                    if cd chaperootodo_client; then git pull; else git clone https://gitlab.com/qacdevops/chaperootodo_client.git; fi
                }
            }
            stage('Deploy'){
                sudo docker-compose pull && sudo -E DB_PASSWORD=${DB_PASSWORD} docker-compose up -d
            }
        }
}
