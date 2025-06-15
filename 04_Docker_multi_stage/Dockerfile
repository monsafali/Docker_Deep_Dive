# Stage 1 ----- build stage
FROM node:22-alpine AS builder



  WORKDIR /app

  COPY package*.json ./

  RUN npm install

  COPY . .


# Stage 2 ----- production stage

FROM node:22-alpine

WORKDIR /app

COPY --from=builder /app /app

ENV PORT=3000

CMD ["node", "index.js"]