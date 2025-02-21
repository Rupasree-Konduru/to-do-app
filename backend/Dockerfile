FROM node:14-alpine3.12

WORKDIR /app
COPY backend /app

RUN npm install  # Ensure dependencies are installed

EXPOSE 4000
CMD ["node", "index.js"]
