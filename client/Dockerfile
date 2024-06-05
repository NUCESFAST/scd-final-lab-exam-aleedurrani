FROM node:14 AS build
# My roll no is 1129
WORKDIR /1129/frontend

COPY package*.json ./

RUN npm install

COPY . .

RUN npm run build

FROM nginx:alpine

COPY --from=build 1129/frontend/build 1129/share/nginx/html


# My roll no is 1129 but my backend service auth is running on 1129 so i gave this 1135
EXPOSE 1135

CMD ["nginx", "-g", "daemon off;"]
