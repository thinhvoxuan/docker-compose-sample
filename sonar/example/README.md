# docker-sonar-scanner-example
usage example of docker-sonar-scanner

This tutorial is meant for when you don't have a Contiouns Integration plataform, your IT administrator is an asshole and you need to quick scan your project with sonar locally on your computer.

1) Create a Dockerfile with this inside in the same folder of your project:

FROM mercuriete/sonar-scanner:onbuild

2) Have a look into the docker-compose.yml

3) start a sonar instance somehow.

4) start the sonar-scanner container.
  This container tries to scan the code and then it connects to sonar to write report.
