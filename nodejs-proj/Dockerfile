# Use the Node.js slim image
FROM node:20-slim

WORKDIR /nodeapp

COPY src/package.json .

RUN npm install 

COPY src/ . 

EXPOSE 3000 

CMD ["npm" , "start"]




