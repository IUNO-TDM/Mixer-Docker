FROM maven:alpine

VOLUME root/.m2
VOLUME root/.PaymentService

# Create app directory

RUN mkdir -p /usr/src/app
WORKDIR /usr/src/app

COPY PaymentService/pom.xml /usr/src/app

RUN mvn verify clean --fail-never

# Adding source, compile and package into a fat jar
COPY PaymentService/src /usr/src/app/src

RUN mvn verify

EXPOSE 8080

CMD mvn jetty:run -Dlistening-interface=0.0.0.0 -DwalletSeed=never,use,this,seed,never,use,this,seed,only,use,mixture,control


#FROM maven:latest
#RUN mkdir /PaymentService
#COPY PaymentService /PaymentService
#WORKDIR PaymentService
#RUN mvn clean package
#EXPOSE 8080
#CMD ["mvn","jetty:run"]


#FROM maven:latest
#RUN git clone https://github.com/IUNO-TDM/PaymentService.git
#WORKDIR PaymentService
#RUN mvn clean package
#EXPOSE 8080
#CMD ["mvn","jetty:run"]

#FROM maven:latest
#RUN git clone https://github.com/goergch/PaymentService.git
#WORKDIR PaymentService
#RUN mvn clean package
#EXPOSE 8080
#CMD ["mvn","jetty:run"]
