from node:12-alpine as builder
workdir /app
copy ./package.json ./
run yarn install
copy . .
run yarn run build

from nginx
expose 3000
copy ./nginx/default.conf /etc/nginx/conf.d/default.conf
copy --form=builder /app/build /usr/share/nginx/html
