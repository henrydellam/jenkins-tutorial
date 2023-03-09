pipeline{
        agent any
        stages{
            stage('Clone'){
                steps{
                    folder="chaperootodo_client"
                    if ! git clone https://gitlab.com/qacdevops/chaperootodo_client.git "${folder}" 2>/dev/null && [ -d "${folder}" ] ; then
                        echo "Clone failed because the folder ${folder} exists"
                    fi
                }
            }
            stage('Deploy'){
                sudo docker-compose pull && sudo -E DB_PASSWORD=${DB_PASSWORD} docker-compose up -d
            }
        }
}
