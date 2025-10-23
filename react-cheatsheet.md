# 📘 ReactJS Command Cheat Sheet

## 🚀 Khởi tạo dự án React

```bash
npx create-react-app my-app
cd my-app
npm start
```

## 📦 Cài đặt thư viện phổ biến

```bash
npm install react-router-dom
npm install axios
npm install redux react-redux
npm install styled-components
npm install gh-pages --save-dev
```

## 🧪 Chạy ứng dụng

```bash
npm start       # Chạy server dev
npm run build   # Build bản production
npm test        # Chạy test với Jest
```

## 🌐 Deploy lên GitHub Pages

```bash
npm run build
npm run deploy
```

> Đảm bảo đã cấu hình `homepage` và script `deploy` trong `package.json`

## 🔍 Kiểm tra phiên bản

```bash
npm list react
npm list react-dom
npm list typescript
```

## 🧹 Dọn dẹp và cài lại

```bash
rm -rf node_modules package-lock.json
npm install
```

## 🧰 Hooks cơ bản

```js
useState()       // Quản lý state
useEffect()      // Side effects
useContext()     // Quản lý context
useRef()         // Tham chiếu DOM
useCallback()    // Ghi nhớ hàm
useMemo()        // Ghi nhớ giá trị
```

## 📁 Cấu trúc thư mục phổ biến

```
src/
├── components/
├── pages/
├── assets/
├── hooks/
├── App.js
├── index.js
```

## 🧠 Gợi ý ESLint fix

```bash
npm install eslint-plugin-react-hooks --save-dev
```
