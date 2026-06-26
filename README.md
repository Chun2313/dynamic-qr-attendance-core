# 🚀 Smart QR Attendance API (Serverless Microservices)

Hệ thống điểm danh bằng mã **QR Code động** giúp chống gian lận cho lớp học và sự kiện. Dự án được xây dựng trên kiến trúc **Serverless** của AWS và quản lý hạ tầng hoàn toàn bằng mã nguồn **AWS CDK v2 (TypeScript)**.

---

## 🛠️ Yêu cầu cài đặt (Prerequisites)

Trước khi bắt tay vào code hoặc chạy dự án, tất cả các thành viên trong nhóm cần cài đặt sẵn các công cụ sau trên máy cá nhân:

1. **Node.js** (Phiên bản LTS khuyến nghị: `>= 18.x` hoặc `>= 20.x`)
2. **AWS CLI v2** — [Hướng dẫn cài đặt chính thức](https://docs.aws.amazon.com/cli/latest/userguide/getting-started-install.html)
3. **AWS CDK v2 CLI** — Cài đặt toàn cục qua NPM:
   ```bash
   npm install -g aws-cdk

   🚀 Khởi động nhanh (Quick Start)1. Lấy mã nguồn về máyBashgit clone https://github.com/Chun2313/dynamic-qr-attendance-core
cd smart-qr-attendance-api
2. Cài đặt các thư viện phụ thuộcBashnpm install
3. Cấu hình thông tuyến AWS CredentialsMở Terminal/PowerShell và chạy lệnh sau để liên kết với tài khoản AWS chung của nhóm:Bashaws configure
Nhập chính xác AWS Access Key ID, AWS Secret Access Key và chọn mặc định vùng (Region) là ap-southeast-1 (Singapore).4. Khởi tạo móng Cloud (Chỉ làm 1 lần duy nhất)Bashcdk bootstrap aws://<TÀI_KHOẢN_ID_12_SỐ>/ap-southeast-1

📂 Cấu trúc thư mục dự án (Dự kiến)
├── bin/
│   └── aws-cdk-app.ts         # File khởi chạy chính (Nơi ép cứng Region ap-southeast-1)
├── lib/
│   └── aws-cdk-stack.ts       # Nơi định nghĩa hạ tầng (API Gateway, Lambda, DynamoDB...)
├── src/                       # Toàn bộ mã nguồn Backend xử lý logic
│   └── functions/
│       ├── qr-generator/      # Microservice sinh mã QR động theo thời gian
│       └── checkin/           # Microservice quét mã và kiểm tra dữ liệu điểm danh
├── test/                      # Thư mục viết Unit Test cho hạ tầng
├── cdk.json                   # File cấu hình hoạt động của CDK Toolkit
└── package.json               # Quản lý các package và thư viện sử dụng

🔐 Quy định làm việc nhóm (Git Workflow)Không được phép code và commit trực tiếp trên nhánh main.Khi làm tính năng mới, hãy tạo nhánh riêng từ main:git checkout -b feature/ten-tinh-nangSau khi hoàn thành và test thử thành công, tạo Pull Request (PR) trên GitHub để Leader review trước khi gộp (Merge) vào nhánh main.