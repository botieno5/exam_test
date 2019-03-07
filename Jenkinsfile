node {

stage('Clone Repository')
{
checkout scm
}

stage('Show me the files'){
sh "ls -l"
}

stage('Build docker image'){

sh "docker build -t exam:latest ."
}

stage('Docker login to hub and push the image'){
sh "docker login -u 'botieno5' -p 'otieno' "
sh "docker tag exam:latest botieno5/exam:latest"
sh "docker push botieno5/exam:latest"
}

stage('Deploy') {
sh "docker run -d -p 7220:80/tcp exam:latest"
}


}