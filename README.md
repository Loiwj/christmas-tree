# 🎄 Cây Thông Noel 3D Tương Tác Xa Xỉ

> Ứng dụng web cây thông Noel 3D chất lượng cao dựa trên **React**, **Three.js (R3F)** và **Nhận diện cử chỉ AI**.

Dự án này không chỉ là một cây thông, mà là một phòng trưng bày tương tác chứa đựng kỷ niệm. Hàng trăm nghìn hạt, đèn màu lấp lánh và những tấm ảnh Polaroid lơ lửng cùng tạo nên một cây thông Noel xa xỉ. Người dùng có thể điều khiển hình dạng cây (tập hợp/phân tán) và xoay góc nhìn thông qua cử chỉ, trải nghiệm một bữa tiệc thị giác đẳng cấp điện ảnh.

![Project Preview](public/preview.png)
*(Lưu ý: Khuyến nghị tải lên một ảnh chụp màn hình dự án của bạn tại đây)*

## ✨ Tính Năng Nổi Bật

* **Trải Nghiệm Thị Giác Tuyệt Vời**: Thân cây được tạo từ hơn 45,000 hạt phát sáng, kết hợp với hiệu ứng quầng sáng động (Bloom) và ánh sáng rực rỡ, tạo nên bầu không khí mơ mộng.
* **Phòng Trưng Bày Kỷ Niệm**: Ảnh được treo trên cây theo phong cách "Polaroid", mỗi tấm là một vật thể phát sáng độc lập, hỗ trợ render hai mặt.
* **Điều Khiển Cử Chỉ AI**: Không cần chuột, chỉ cần sử dụng camera để bắt cử chỉ là có thể điều khiển hình dạng cây (tập hợp/phân tán) và xoay góc nhìn.
* **Chi Tiết Phong Phú**: Bao gồm đèn màu nhấp nháy động, tuyết vàng bạc rơi, cùng các món quà và kẹo Giáng sinh được phân bố ngẫu nhiên.
* **Tùy Chỉnh Cao**: **Hỗ trợ người dùng dễ dàng thay thế bằng ảnh của mình và tự do điều chỉnh số lượng ảnh.**

## 🛠️ Công Nghệ Sử Dụng

* **Framework**: React 18, Vite
* **3D Engine**: React Three Fiber (Three.js)
* **Thư Viện**: @react-three/drei, Maath
* **Hậu Kỳ**: @react-three/postprocessing
* **AI Thị Giác**: MediaPipe Tasks Vision (Google)

## 🚀 Bắt Đầu Nhanh

### 1. Chuẩn Bị Môi Trường
Đảm bảo máy tính của bạn đã cài đặt [Node.js](https://nodejs.org/) (khuyến nghị phiên bản v18 trở lên).

### 2. Cài Đặt Dependencies
Mở terminal trong thư mục gốc của dự án, chạy lệnh:
```bash
npm install
```

### 3. Khởi Động Dự Án
```bash
npm run dev
```

## 🖼️ Tùy Chỉnh Ảnh

### 1. Chuẩn Bị Ảnh
Tìm thư mục `public/photos/` trong thư mục dự án.

**Ảnh lớn trên đỉnh/ảnh bìa**: Đặt tên là `top.jpg` (sẽ hiển thị trên ngôi sao 3D ở đỉnh cây).

**Ảnh trên thân cây**: Đặt tên là `1.jpg`, `2.jpg`, `3.jpg` ... và tiếp tục như vậy.

**Khuyến nghị**: Sử dụng ảnh vuông hoặc tỷ lệ 4:3, kích thước file không nên quá lớn (khuyến nghị mỗi ảnh dưới 500kb để đảm bảo hiệu suất mượt mà).

### 2. Thay Thế Ảnh
Chỉ cần sao chép ảnh của bạn vào thư mục `public/photos/`, ghi đè lên ảnh hiện có. Vui lòng giữ nguyên định dạng tên file (`1.jpg`, `2.jpg`, v.v.).

### 3. Thay Đổi Số Lượng Ảnh (Tăng hoặc Giảm)
Nếu bạn đã thêm nhiều ảnh hơn (ví dụ: từ mặc định 31 ảnh tăng lên 100 ảnh), cần chỉnh sửa code để thông báo cho chương trình tải chúng.

Mở file: `src/App.tsx`

Tìm dòng code khoảng **dòng 19**:
```typescript
// --- 动态生成照片列表 (top.jpg + 1.jpg 到 31.jpg) ---
const TOTAL_NUMBERED_PHOTOS = 31; // <--- Sửa số này!
```

## 🖐️ Hướng Dẫn Điều Khiển Cử Chỉ

* **Dự án này có tích hợp hệ thống nhận diện cử chỉ AI, vui lòng đứng trước camera để thao tác (có nút DEBUG ở góc dưới bên phải màn hình để xem hình ảnh camera)**:

| Cử Chỉ | Hành Động | Mô Tả |
|--------|-----------|-------|
| 🖐 Mở lòng bàn tay (Open Palm) | Disperse (Phân Tán) | Cây thông Noel nổ tung thành hàng nghìn hạt và ảnh bay lơ lửng |
| ✊ Nắm chặt tay (Closed Fist) | Assemble (Tập Hợp) | Tất cả các phần tử ngay lập tức tập hợp lại thành một cây thông Noel hoàn hảo |
| 👋 Di chuyển tay trái/phải | Xoay Góc Nhìn | Tay trái → cây xoay trái; Tay phải → cây xoay phải |
| 👋 Di chuyển tay lên/xuống | Góc Nhìn Lên/Xuống | Tay lên → góc nhìn nâng cao; Tay xuống → góc nhìn hạ thấp |

## ⚙️ Cấu Hình Nâng Cao

* **Nếu bạn quen thuộc với code, có thể điều chỉnh thêm các tham số hình ảnh trong object CONFIG trong `src/App.tsx`**:

```typescript
const CONFIG = {
  colors: { ... }, // Sửa màu cây, đèn, viền
  counts: {
    foliage: 15000,   // Sửa số lượng hạt lá (cấu hình thấp có thể bị lag)
    ornaments: 300,   // Sửa số lượng ảnh/Polaroid treo
    lights: 400       // Sửa số lượng đèn màu
  },
  tree: { height: 22, radius: 9 }, // Sửa kích thước cây
  // ...
};
```

## 📄 Giấy Phép

MIT License. Tự do sử dụng và chỉnh sửa cho lễ kỷ niệm ngày lễ của riêng bạn!

## Merry Christmas! 🎄✨
