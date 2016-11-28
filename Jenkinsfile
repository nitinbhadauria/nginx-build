node {
  stage 'Checkout'
  git credentialsId: '2d384dfd-f3ef-432c-b6d9-ac572701cf5e', url: 'git@gitlab.com:nitin.bhadauria/hello-world.git'
 
  stage 'Docker build'
  docker.build('nginx-demo')

  stage 'Docker push'
  docker.withRegistry ('https://172.16.20.24:5000/v1/users/', 'f18fbde4-00bd-4055-b239-803c038754a9') {
    docker.image('nginx-demo').push('latest')
  }
}