FROM beevelop/ionic:latest AS ionic
#Create app directory 
WORKDIR /usr/src/app
#Install app dependencies
#A wildcard is used to ensure both package.json and package-lock.json are copied where available 
COPY package*.json ./
RUN npm ci
#bundle app source
COPY . .
RUN ionic build
## Run
FROM nginx:alpine
#copy www /usr/share/nginx/html
COPY --from=ionic /usr/src/app/www /usr/share/nginx/html
