FROM node:18.20.3-alpine

WORKDIR /src

COPY package*.json /src

RUN npm ci

COPY . /src

RUN npm run build


CMD npm start

#
# NOTES:
# In package.json file make the following change:
# "scripts": {
#    ...
#    "start": "ng serve --host 0.0.0.0",
#    ...
#  }
#
# Ref answer by Hans Kilian on S.O.:
# https://stackoverflow.com/questions/74467776/problem-connecting-to-angular-app-in-docker
#
#
# Ref Docker / Angular live-reload ...
# https://www.freecodecamp.org/news/how-to-enable-live-reload-on-docker-based-applications/
#
# docker volume create nodemodules
# docker run --name app -p 4200:4200 -v nodemodules:/src/node_modules  -v .:/src  ngcourse
#

