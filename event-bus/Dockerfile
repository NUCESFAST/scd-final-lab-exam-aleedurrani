FROM node:14

# My Roll No is 1129
WORKDIR /1129/backend_eventBus

COPY package*.json ./

RUN npm install

COPY . .

# 1129+2000+2
EXPOSE 3131

CMD ["node", "index.js"]
