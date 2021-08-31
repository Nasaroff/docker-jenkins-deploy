# Stage 1: Build
FROM node:lastest as node

WORKDIR /app

COPY . /app

RUN npm install

RUN npm run build

# Stage 2: Run
FROM nginx:alpine
COPY --from=node /app/dist/frontend usr/share/nginx/html
COPY --from=node /app/nginx/nginx.conf /etc/nginx/nginx.conf

EXPOSE 4200