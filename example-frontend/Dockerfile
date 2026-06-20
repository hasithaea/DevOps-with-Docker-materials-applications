FROM node:16-alpine AS build-stage
    
WORKDIR /myapp    

COPY . .
ENV REACT_APP_BACKEND_URL=http://localhost/api

RUN npm install && \
    npm run build

FROM nginx:1.19-alpine

COPY --from=build-stage /myapp/build /usr/share/nginx/html

EXPOSE 80
