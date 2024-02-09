FROM eclipse-temurin:17-jdk-alpine
VOLUME /tmp
COPY ./package.json .
EXPOSE 8080
ENTRYPOINT ["npm"]
CMD ["npm", "start"]
