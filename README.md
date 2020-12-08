# jenkin_pipeline

https://medium.com/@amitvermaa93/jenkins-setup-windows-1e253682aa53

https://www.youtube.com/watch?v=-VaVmb_UOC8

https://www.eficode.com/blog/jenkins-groovy-tutorial

CI CD Of Docker Containers | DevOps | Jenkins Pipeline Tutorial | Docker CI/CD | DevOps CI/CD : https://www.youtube.com/watch?v=gdbA3vR2eDs

jenkins installation trouble shoot ing :: https://stackoverflow.com/questions/50718320/java-lang-nosuchmethoderror-no-such-dsl-method-pipeline-found-when-running

---------------------------------------------------------
JaCoCo End-to-End Code Coverage at Runtime  : https://dzone.com/articles/code-coverage-report-generator-for-java-projects-a
------------------------------------------------------
-------------------------------------------------------------------------
1. pass javaagent as a VM argument while running the application.
------------------------------------------------------------------------------ 
java -javaagent:jacocoagent.jar=destfile=C:\Users\a124kuma\Documents\AkNokia\git\POC\spring-boot-rest-api-master\src\main\java\jacoco-unit.exec -jar C:\Users\a124kuma\Documents\AkNokia\git\POC\spring-boot-rest-api-master\target\spring-boot-testing-0.0.1-SNAPSHOT.jar


-------------------------------------------------------------------------
2. use jacococli - this will generate the report in html,xml etc format
-------------------------------------------------------------------------------
example::::::::::::::::

java -jar lib/jacococli.jar report path/to/jacoco.exec --classfiles path/to/your.jar --html path/for/report

java -jar lib/jacococli.jar report C:\Users\a124kuma\Documents\AkNokia\git\POC\spring-boot-rest-api-master\target\coverage-reports\jacoco-unit.exec --classfiles C:\Users\a124kuma\Documents\AkNokia\git\POC\spring-boot-rest-api-master\target\classes\id --sourcefiles C:\Users\a124kuma\Documents\AkNokia\git\POC\spring-boot-rest-api-master\src\main\java --html C:\Users\a124kuma\Documents\AkNokia\git\POC\spring-boot-rest-api-master\src\main\java

----------------------------------------------------------------------------
3. push this generate reports from different modules to sonarqeue
--------------------------------------------------------------------------

sonar:sonar -Dsonar.coverage.jacoco.xmlReportPaths=${WORKSPACE}/modules_1/target/site/jacoco-aggregate/jacoco.xml,${WORKSPACE}/modules_2/target/site/jacoco-aggregate/jacoco.xml
