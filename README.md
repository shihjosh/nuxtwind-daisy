<p style="text-align: center">
  <img style="width: 900px" src="Nuxtwind Daisy Banner.jpg"/>
</p>

<h1 align="center">Nuxtwind Daisy 🟢💨🌼</h1>
<p style="text-align: center">
Nuxtwind Daisy is a starter template for Nuxt.js 3 + Tailwind CSS + Daisy UI with additional installed setup for custom font, icons, animation, and more.
</p>

- [Showcase](#showcase)
- [Getting Started Guide](#getting-started-guide)

# 問題
 - Nuxtjs3 靜態圖片 有問題 我將嘗試 把public 目錄同步 assets 資料與路徑
   這樣開發能看到圖片， generate 時也抓地到圖片。

 - 透過 strapi 取的 markdwon 取得文章資料 顯示在前台網頁
   解噘方法:https://github.com/nuxt-community/markdownit-module/issues/47#issuecomment-1345268133

# API Install strapi to docker
### 環境:
 - Nodejs V16
 - Strapi
 
##### create strapi-app
 
```sh
npx create-strapi-app@v4.3.8 app
```
##### ADD Dockerfile
 
```yaml
FROM node:16

# Installing libvips-dev for sharp Compatibility

RUN apt-get update && apt-get install libvips-dev -y

ARG NODE_ENV=development

ENV NODE_ENV=${NODE_ENV}

WORKDIR /opt/

COPY ./package.json ./package-lock.json ./

ENV PATH /opt/node_modules/.bin:$PATH

RUN npm install

WORKDIR /opt/app

COPY ./ .

RUN npm run build

EXPOSE 1337

CMD ["npm", "run", "develop"]
```
 
##### Build Image

```sh
docker build -t mystrapi:v01 .
```

#### docker-compose test

```yaml

version: '3'
services:
  strapi:
    image: mystrapi:v01
    environment:
      DATABASE_CLIENT: mysql
      DATABASE_HOST: 192.168.50.114
      DATABASE_PORT: 3306
      DATABASE_NAME: strapi
      DATABASE_USERNAME: root
      DATABASE_PASSWORD: root
      DATABASE_SSL: 'false'
    ports:
      - '1339:1337'

```


