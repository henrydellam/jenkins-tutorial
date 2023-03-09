pipeline{
        agent any
        stages{
            stage('Clone'){
                steps{
                    sh "folder='chaperootodo_client'
                        if ! git clone https://gitlab.com/qacdevops/chaperootodo_client.git "${folder}" 2>/dev/null && [ -d "${folder}" ] ; 
                        then
                            echo "Clone skipped because the folder ${folder} exists"
                            git pull 
                        fi
                        "
                }
            }
            stage('Deploy'){
                steps{
                        sh "DB_PASSWORD=password"
                        sh "sudo docker-compose pull && sudo -E DB_PASSWORD=${DB_PASSWORD} docker-compose up -d"
                }
            }
        }
}
