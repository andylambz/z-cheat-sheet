
# 🖥️ Windows Command Line Cheat Sheet – Quản lý File & Thư Mục

## 📁 Tạo, di chuyển và hiển thị thư mục

```cmd
mkdir <dir_name>          # Tạo thư mục mới
cd <dir_name>             # Di chuyển vào thư mục
cd ..                     # Quay lại thư mục cha
cd                        # Hiển thị đường dẫn hiện tại
dir                       # Hiển thị danh sách file và thư mục
dir /q /s                 # Hiển thị chi tiết và thư mục con
```

## 📄 Tạo, xóa và di chuyển file

```cmd
type nul > TenFile.txt            # Tạo file rỗng
del TenFile.txt                   # Xóa file cụ thể
del *.txt                         # Xóa tất cả file .txt
move TenFile.txt ThuMucDich\      # Di chuyển file vào thư mục
```

## 🧹 Xóa thư mục và dọn dẹp

```cmd
rmdir TenThuMuc /s /q     # Xóa thư mục và toàn bộ nội dung
                          # /s: xóa cả thư mục con
                          # /q: không hỏi xác nhận
rm -rf node_modules       # (dùng trong môi trường Node.js)
cls                       # Xóa màn hình console
```

## 🔍 Tìm kiếm và kiểm tra

```cmd
dir /s /b TenFile.txt     # Tìm file theo tên (hiển thị đường dẫn đầy đủ)
npm list react            # Kiểm tra phiên bản React (nếu dùng Node.js)
npm list typescript       # Kiểm tra phiên bản TypeScript
```

## 🧠 Lệnh tiện ích khác

```cmd
echo Hello                # In ra dòng chữ "Hello"
exit                      # Thoát khỏi Command Prompt
```
