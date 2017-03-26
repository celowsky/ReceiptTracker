FROM node:7

COPY ./app.js           /usr/src/app/
COPY ./package.json     /usr/src/app/

EXPOSE 3000

WORKDIR /usr/src/app/

# Adds Tini for Node.js kernel signal handling
# See (https://github.com/nodejs/docker-node/blob/master/docs/BestPractices.md)
ENV TINI_VERSION v0.14.0
ADD https://github.com/krallin/tini/releases/download/${TINI_VERSION}/tini /tini
RUN chmod +x /tini
ENTRYPOINT ["/tini", "--"]

CMD ["node", "app.js", "-u", "\"node\""]
