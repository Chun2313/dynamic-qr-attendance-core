🚀 Smart QR Attendance API (Serverless Microservices)
Hệ thống điểm danh bằng mã QR Code động giúp chống gian lận cho lớp học và sự kiện. Dự án được xây dựng trên kiến trúc Serverless của AWS và quản lý hạ tầng hoàn toàn bằng mã nguồn AWS CDK v2 (TypeScript).


🛠️ Yêu cầu cài đặt (Prerequisites)
Trước khi bắt tay vào code hoặc chạy dự án, tất cả các thành viên trong nhóm cần cài đặt sẵn các công cụ sau trên máy cá nhân:

Node.js (Phiên bản LTS khuyến nghị: >= 18.x hoặc >= 20.x)
AWS CLI v2 — Hướng dẫn cài đặt chính thức
AWS CDK v2 CLI — Cài đặt toàn cục qua NPM:

npm install -g aws-cdk


🚀 Khởi động nhanh (Quick Start)
1. Lấy mã nguồn về máy
git clone https://github.com/Chun2313/dynamic-qr-attendance-core

cd smart-qr-attendance-api
2. Cài đặt các thư viện phụ thuộc
npm install
3. Cấu hình thông tuyến AWS Credentials
Mở Terminal/PowerShell và chạy lệnh sau để liên kết với tài khoản AWS chung của nhóm:

aws configure

Nhập chính xác AWS Access Key ID, AWS Secret Access Key và chọn mặc định vùng (Region) là ap-southeast-1 (Singapore).
4. Khởi tạo móng Cloud (Chỉ làm 1 lần duy nhất)
cdk bootstrap aws://<TÀI_KHOẢN_ID_12_SỐ>/ap-southeast-1


💻 Các lệnh CLI hữu ích thường dùng
Trong quá trình phát triển dự án, bạn sẽ thường xuyên sử dụng các lệnh sau:

Lệnh
Chức năng
npm run build
Biên dịch toàn bộ code TypeScript sang JavaScript
npm run watch
Chế độ "theo dõi" — tự động biên dịch mỗi khi có file thay đổi
npx cdk synth
Xuất và kiểm tra file thiết kế CloudFormation Template
npx cdk diff
So sánh sự khác biệt giữa code local và hạ tầng đang chạy trên AWS
npx cdk deploy
Triển khai (Deploy) trực tiếp hạ tầng và code Lambda lên AWS
npx cdk destroy
Xóa sạch toàn bộ tài nguyên đã deploy trên AWS (Cẩn thận khi dùng)
npm run test
Chạy hệ thống Unit Test (Sử dụng Jest)



📁 Cấu trúc thư mục dự án (Dự kiến)
├── bin/

│   └── aws-cdk-app.ts      # File khởi chạy chính (Nơi ép cứng Region ap-southeast-1)

├── lib/

│   └── aws-cdk-stack.ts    # Nơi định nghĩa hạ tầng (API Gateway, Lambda, DynamoDB...)

├── src/                    # Toàn bộ mã nguồn Backend xử lý logic

│   └── functions/

│       ├── qr-generator/   # Microservice sinh mã QR động theo thời gian

│       └── checkin/        # Microservice quét mã và kiểm tra dữ liệu điểm danh

├── test/                   # Thư mục viết Unit Test cho hạ tầng

├── cdk.json                # File cấu hình hoạt động của CDK Toolkit

└── package.json            # Quản lý các package và thư viện sử dụng


🔐 Quy định làm việc nhóm (Git Workflow)
Không được phép code và commit trực tiếp trên nhánh main.
Khi làm tính năng mới, hãy tạo nhánh riêng từ main:

git checkout -b feature/ten-tinh-nang

Sau khi hoàn thành và test thử thành công, tạo Pull Request (PR) trên GitHub để Leader review trước khi gộp (Merge) vào nhánh main.

