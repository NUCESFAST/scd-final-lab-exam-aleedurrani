FROM node:14

# My Roll No is 1129
WORKDIR /1129/backend_classrooms

COPY package*.json ./

RUN npm install

COPY . .

# 1129+2000+1
EXPOSE 3130

CMD ["node", "index.js"]
