FROM {{ cookiecutter.image }}

ENV NODE_PATH /usr/lib/node_modules/

RUN mkdir /service
WORKDIR /service

COPY package.json /service
RUN npm install

COPY client.js /service

CMD ["node", "client.js"]
