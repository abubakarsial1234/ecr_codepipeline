# Frontend Dockerfile
FROM node:16

WORKDIR /app

COPY package.json ./ 
RUN npm install

COPY . .

# Give execute permissions to react-scripts to avoid permission denied error
RUN chmod +x ./node_modules/.bin/react-scripts

RUN npm run build

# Serve frontend build using simple http server
RUN npm install -g serve

EXPOSE 3000

CMD ["serve", "-s", "build", "-l", "3000"]
