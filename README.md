# Hướng dẫn cài đặt và chạy dự án Paycard

## 1. Cài đặt dự án
```sh
npm install
```

## 2. Khắc phục lỗi
### 2.1. Lỗi thiếu cấu hình ESLint
#### Lỗi:
```bash
[eslint] No ESLint configuration found in /Users/truongdat/Desktop/paycard/src.
```
#### Cách khắc phục:
Thêm file `.eslintrc.js` vào thư mục gốc của dự án (`paycard/`) với nội dung sau:  
```javascript
module.exports = {
  root: true,
  env: {
    node: true
  },
  extends: [
    "plugin:vue/vue3-essential",
    "eslint:recommended"
  ],
  parserOptions: {
    ecmaVersion: 2021
  },
  rules: {}
};
```
Sau đó, cài đặt ESLint:
```sh
npm install --save-dev eslint
```

### 2.2. Lỗi thiếu package `vue-i18n`
#### Lỗi:
```bash
Module not found: Error: Can't resolve 'vue-i18n' in '/Users/truongdat/Desktop/paycard/src'
```
#### Cách khắc phục:
```sh
npm install vue-i18n@9
```

### 2.3. Lỗi thiếu `sass-loader`
#### Lỗi:
```bash
Failed to resolve loader: sass-loader
```
#### Cách khắc phục:
```sh
npm install --save-dev sass-loader@latest sass
```

### 2.4. Lỗi phiên bản Node.js không tương thích
#### Lỗi:
```bash
npm warn EBADENGINE Unsupported engine {
  current: { node: 'v23.4.0', npm: '10.9.2' }
}
```
#### Cách khắc phục:
Dự án chỉ hỗ trợ **Node.js từ 8 đến 22**. Nếu đang dùng Node.js 23, hạ xuống Node.js 20:
```sh
nvm install 20
nvm use 20
```
(Nếu chưa cài `nvm`, tham khảo [hướng dẫn tại đây](https://github.com/nvm-sh/nvm#installing-and-updating))

### 2.5. Cập nhật và sửa lỗi package lỗi thời
```sh
npm audit fix --force
```

## 3. Chạy dự án
```sh
npm run dev
```

Dự án sẽ khởi động trên `http://localhost:8080/` (hoặc cổng khác nếu có thay đổi). 🚀

