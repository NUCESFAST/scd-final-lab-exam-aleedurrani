FROM node:14

# My Roll No is 1129
WORKDIR /1129/backend_post

COPY package*.json ./

RUN npm install

COPY . .

# 1129+2000+3
EXPOSE 3132

CMD ["node", "index.js"]
