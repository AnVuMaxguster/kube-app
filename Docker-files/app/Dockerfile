FROM openjdk:11 as BUILD_ARTIFACT
RUN apt update && apt install maven git -y  
RUN git clone https://github.com/devopshydclub/vprofile-project.git 
RUN cd vprofile-project && git checkout docker && mvn install

FROM tomcat:9-jre11
RUN rm -rf /usr/local/tomcat/webapps/*
COPY --from=BUILD_ARTIFACT vprofile-project/target/vprofile-v2.war /usr/local/tomcat/webapps/ROOT.war
EXPOSE 8080
CMD ["catalina.sh", "run"]