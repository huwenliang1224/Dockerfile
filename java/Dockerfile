FROM daocloud.io/java:openjdk-8u40
RUN mkdir -p /mnt/logs
ADD web.jar /workspace/web/
EXPOSE 8080
WORKDIR /workspace/web/
CMD ["java","-jar","web.jar"]
