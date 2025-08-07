FROM node:18
WORKDIR /app
COPY . .
RUN npm init -y && npm install express
EXPOSE 5000
CMD ["node", "index.js"]