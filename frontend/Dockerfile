# ---------- Stage 1: Build Quasar SPA ----------
FROM node:20-alpine AS builder

WORKDIR /app

# ติดตั้งเครื่องมือที่ Quasar อาจใช้
RUN apk add --no-cache python3 make g++

# Copy package files แล้วลง dependency
COPY package.json package-lock.json* ./
COPY . .

RUN npm ci --legacy-peer-deps

# Build SPA
RUN npm run build


# ---------- Stage 2: Serve ด้วย nginx ----------
FROM nginx:stable-alpine

WORKDIR /usr/share/nginx/html

# ใช้ nginx.conf ของโปรเจกต์เรา (ถ้ามี)
COPY nginx.conf /etc/nginx/conf.d/default.conf

# Copy ไฟล์ที่ build แล้วจาก Quasar
COPY --from=builder /app/dist/spa/ .

# Copy standalone HTML page
# ❗ ต้องมีไฟล์ src/pages/index_name.html จริง ไม่งั้น build error
COPY ./src/pages/index_name.html ./index_name.html

EXPOSE 80

CMD ["nginx", "-g", "daemon off;"]
