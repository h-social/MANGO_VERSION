# 📦 Versioned Releases via IIS

Repository này được sử dụng để triển khai và quản lý các bản cập nhật phần mềm thông qua IIS

## 📁 Cấu trúc thư mục

.gitignore # Bỏ qua các file không cần track
Version/ # Chứa các bản cập nhật phân theo version
update.xml # File mô tả thông tin phiên bản hiện tại

## 🔧 Cách hoạt động

1. Client truy cập đường dẫn `https://cdn.jsdelivr.net/gh/h-social/MANGO_VERSION@main/update.xml` để kiểm tra phiên bản mới.
2. Nếu phiên bản mới hơn, client sẽ tải về file từ thư mục `Version/vX.X.X/`.
3. Các bản phát hành được quản lý qua Git để đảm bảo theo dõi chặt chẽ.

## 🛠 Quy trình cập nhật phiên bản

1. Build ứng dụng và tạo thư mục `Version/vX.Y.Z/`.
2. Copy file cài đặt hoặc update vào đó.
3. Cập nhật `update.xml` với thông tin version mới.
4. Commit và push lên Git nếu cần.
5. github sẽ tự động cập nhật nội dung mới qua cdn.

## 🧾 Mẫu `update.xml`

```xml
<?xml version="1.0" encoding="utf-8"?>
<updates>
  <release>
    <version>1.1.0</version>
    <url>http://yourdomain/Version/v1.1.0/YourApp.exe</url>
    <mandatory>false</mandatory>
  </release>
</updates>
