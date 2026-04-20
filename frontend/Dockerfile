FROM node:18

WORKDIR /app

COPY package.json package-lock.json ./

RUN npm config set fetch-timeout 600000 \
 && npm config set registry https://registry.npmjs.org/ \
 && npm ci

COPY . .

RUN npm run build

CMD ["npx", "-y", "http-server", "-p", "8000", "/app/build"]