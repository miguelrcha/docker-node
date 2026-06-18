FROM node:18-alpine

WORKDIR /app

COPY package*.json ./
RUN npm install --production

COPY . .

RUN addgroup -S dockernode && adduser -S appuser -G dockernode
RUN chown -R appuser:dockernode /app

USER appuser

EXPOSE 5000

CMD ["node", "server.js"]
