See https://danielveselka.blogspot.com/2020/12/deploy-java-ee-8-application-into-jboss.html 

# Build
mvn clean package && docker build -t com.dave/java-ee8-minimal .

# RUN on JBoss Wildfly

docker run -it --name java-ee8-minimal com.dave/java-ee8-minimal

# RUN on Glassfish

docker rm -f java-ee8-minimal || true && docker run -d -p 8080:8080 -p 4848:4848 --name java-ee8-minimal com.dave/java-ee8-minimal 
