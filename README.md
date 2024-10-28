# Continuous Integration and Continuous Deployment (CI/CD) with Jenkins
## Giới thiệu
Tài liệu này cung cấp tổng quan về việc thiết lập một pipeline CI/CD sử dụng Jenkins. Jenkins là một máy chủ tự động hóa mã nguồn mở giúp tự động hóa các phần của phát triển phần mềm liên quan đến xây dựng, kiểm thử và triển khai, tạo điều kiện cho tích hợp liên tục và phân phối liên tục.

### CI và CD là gì?
- **CI (Continuous Integration - Tích hợp liên tục)**: Là quá trình tự động hóa việc tích hợp mã nguồn từ nhiều nhà phát triển vào một nhánh chính. Mỗi lần tích hợp sẽ được kiểm thử tự động để phát hiện lỗi sớm. (build, test)
- **CD (Continuous Delivery - Phân phối liên tục)**: Là quá trình tự động hóa việc triển khai mã nguồn đã được kiểm thử vào môi trường sản xuất hoặc môi trường staging. Điều này giúp đảm bảo rằng phần mềm luôn sẵn sàng để phát hành. (build, push, k8s, docker)

## Điều kiện tiên quyết
- Đã cài đặt và chạy Jenkins
- Hiểu biết cơ bản về các công việc và pipeline của Jenkins
- Kho mã nguồn (ví dụ: GitHub, GitLab)

## Thiết lập Jenkins

### Bước 1: Cài đặt Jenkins
Làm theo hướng dẫn cài đặt Jenkins chính thức cho hệ điều hành của bạn: [Hướng dẫn cài đặt Jenkins](https://www.jenkins.io/doc/book/installing/)

### Bước 2: Cấu hình Jenkins
1. Mở Jenkins trong trình duyệt web của bạn.
2. Cài đặt các plugin cần thiết (ví dụ: Git, Pipeline).
3. Cấu hình các công cụ toàn cầu (ví dụ: JDK, Git).

## Tạo một Pipeline CI/CD

### Bước 1: Tạo một công việc Pipeline mới
1. Mở bảng điều khiển Jenkins.
2. Nhấp vào `New Item`.
3. Nhập tên cho công việc của bạn và chọn `Pipeline`, sau đó nhấp `OK`.

### Bước 2: Định nghĩa Pipeline
1. Trong trang cấu hình pipeline, cuộn xuống phần `Pipeline`.
2. Chọn `Pipeline script` và định nghĩa pipeline của bạn sử dụng cú pháp Jenkinsfile.

### Ví dụ Jenkinsfile
```groovy
pipeline {
    agent any

    stages {
        stage('Build') {
            steps {
                echo 'Building...'
                // Thêm các bước xây dựng ở đây
            }
        }
        stage('Test') {
            steps {
                echo 'Testing...'
                // Thêm các bước kiểm thử ở đây
            }
        }
        stage('Deploy') {
            steps {
                echo 'Deploying...'
                // Thêm các bước triển khai ở đây
            }
        }
    }
}
```

### Bước 3: Lưu và chạy Pipeline
1. Nhấp `Save` để lưu cấu hình pipeline của bạn.
2. Nhấp `Build Now` để chạy pipeline.

## Kết luận
Bạn đã thiết lập một pipeline CI/CD cơ bản sử dụng Jenkins. Tùy chỉnh các giai đoạn và bước theo yêu cầu của dự án của bạn để tự động hóa hoàn toàn các quy trình xây dựng, kiểm thử và triển khai.

Để biết thêm các cấu hình và tính năng nâng cao, tham khảo [Tài liệu Jenkins](https://www.jenkins.io/doc/).

