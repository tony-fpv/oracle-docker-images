#!groovy

node {

  stage 'Building docker env'
  def dbImage = docker.build('oracle', 'docker/oracle')
  def wlpImage = docker.build('liberty', 'docker/liberty')


  stage 'Running maven build'
  git url: 'https://github.com/tony-fpv/oracle-docker-images.git', branch: 'docker'
  def mvnHome = tool 'maven 3.3.9'
  sh "${mvnHome}/bin/mvn -B clean install"
}
