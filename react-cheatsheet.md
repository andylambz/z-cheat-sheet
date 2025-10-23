# 📘 ReactJS Command Cheat Sheet

## 🚀 Khởi tạo dự án React

```bash
npx create-react-app <my-app>
cd <my-app>
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

## 🧪 Kiểm tra và gỡ lỗi

```bash
npm list                   # Hiển thị toàn bộ cây phụ thuộc
npm list react             # Kiểm tra phiên bản React đang dùng
npm list typescript        # Kiểm tra phiên bản TypeScript
npm ls <package>           # Kiểm tra package cụ thể
```

## 🧹 Dọn dẹp và cài lại

```bash
rm -rf node_modules package-lock.json
npm cache clean --force
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

***

# 🧩 ReactJS Advanced Command Cheat Sheet

## 📦 Quản lý package nâng cao

```bash
npm outdated               # Kiểm tra các package đã lỗi thời
npm update                 # Cập nhật các package lên phiên bản mới nhất
npm audit                  # Kiểm tra lỗ hổng bảo mật
npm audit fix              # Sửa lỗi bảo mật tự động
npm install <pkg>@latest   # Cài phiên bản mới nhất của một package
```

## 🧪 Testing nâng cao với Jest và React Testing Library

```bash
npm install --save-dev jest @testing-library/react @testing-library/jest-dom
npm test
```

## 🧬 Hooks nâng cao

```js
useReducer()     // Quản lý state phức tạp
useLayoutEffect() // Chạy đồng bộ sau render
useImperativeHandle() // Tùy chỉnh ref từ component con
```
