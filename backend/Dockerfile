FROM node:22 as builder
WORKDIR /backend
COPY package*.json .
RUN npm install
COPY . .

FROM node:22-alpine as stage
WORKDIR /backend
COPY --from=builder /backend .
EXPOSE 5000
CMD ["npm", "start"]
