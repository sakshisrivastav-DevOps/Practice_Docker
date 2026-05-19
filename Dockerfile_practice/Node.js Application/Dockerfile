FROM node:latest
#WORKDIR /app
COPY . /usr/local/lib/node_modules/
RUN npm install --omit=dev
COPY . .
CMD ["node", "server.js"]
EXPOSE 3000
