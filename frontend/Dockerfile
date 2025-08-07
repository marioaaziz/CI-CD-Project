FROM node:18
WORKDIR /app
COPY . .
RUN npx create-react-app myapp && \
    cd myapp && \
    npm install && \
    npm run build
EXPOSE 3000
CMD ["npx", "serve", "-s", "myapp/build"]