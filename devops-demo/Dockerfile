FROM node:25 AS build
WORKDIR /app
COPY package.json* .
COPY . .
RUN npm install

FROM node:25-alpine AS runtime
WORKDIR /app
COPY --from=build /app .
CMD ["node", "app.js"]